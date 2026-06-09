# RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>> &,CommandFlags)

- ea: `0x18006fdac`
- end: `0x180070a29`
- name: `?CreateText@?$Table@VPackageSources@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageSources@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@23@W4CommandFlags@@@Z`
- size: `3197`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006e8e0`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18006ec14`
- `0x18006fdac`
- `0x1800721b0`
- `0x180072270`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800702b2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180070318`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800702b2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180070318`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800702ab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180070311`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800702ab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180070311`

## string_xrefs

- `0x1800700d3`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18007009c`: `CREATE TABLE IF NOT EXISTS `
- `0x180070984`: `CREATE TABLE IF NOT EXISTS `
- `0x180070188`: ` AS incoming, `
- `0x1800705a0`: `REPLACE INTO `
- `0x1800707e8`: `UPDATE `

## pseudocode

```c
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::CreateText(
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
  _BYTE v102[12]; // [rsp+158h] [rbp+50h] BYREF
  int v103; // [rsp+164h] [rbp+5Ch]
  __m128i si128; // [rsp+168h] [rbp+60h]
  void *v105[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v106; // [rsp+188h] [rbp+80h]
  _QWORD v107[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v108; // [rsp+1A8h] [rbp+A0h]
  __int128 v109; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v110; // [rsp+1C8h] [rbp+C0h]
  void *Block[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v112; // [rsp+1E8h] [rbp+E0h]
  _QWORD v113[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v114; // [rsp+208h] [rbp+100h]

  v7 = 0;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::IndexName(v107);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v102, "PackageSourc", sizeof(v102));
    v103 = *(unsigned __int16 *)"es";
    v8 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v9 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v9 = *(_BYTE **)v102;
    v10 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v8, (__int64)v9, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v10, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v11,
      2050,
      (unsigned int)v107,
      (_DWORD)a1 + 448,
      (__int64)v98);
    v12 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" FROM ");
    v13 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v13 = (_QWORD *)v107[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, (__int64)v13, v108.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v14,
      16,
      (unsigned int)v107,
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
    *(_OWORD *)v105 = 0;
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v105, "id");
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)v105, 2u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    std::string::_Tidy_deallocate(v105);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::MapName(v113);
    v32 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v33 = v113;
    if ( v114.m128i_i64[1] > 0xFuLL )
      v33 = (_QWORD *)v113[0];
    v34 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v32, (__int64)v33, v114.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v34,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v35 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"INSERT INTO ");
    v36 = v113;
    if ( v114.m128i_i64[1] > 0xFuLL )
      v36 = (_QWORD *)v113[0];
    v37 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v35, (__int64)v36, v114.m128i_u64[0]);
    v38 = std::operator<<<std::char_traits<char>>(v37, (__int64)" SELECT ");
    v39 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v39 = (_QWORD *)v107[0];
    v40 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v38, (__int64)v39, v108.m128i_u64[0]);
    v41 = std::operator<<<std::char_traits<char>>(v40, (__int64)".");
    *(_OWORD *)v105 = 0;
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v105, "id");
    v42 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v41, (__int64)v105, 2u);
    v43 = std::operator<<<std::char_traits<char>>(v42, (__int64)" AS incoming, ");
    v44 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v44 = *(_BYTE **)v102;
    v45 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v43, (__int64)v44, si128.m128i_u64[0]);
    v46 = std::operator<<<std::char_traits<char>>(v45, (__int64)".");
    *(_OWORD *)Block = 0;
    v112 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)Block, "id");
    v47 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, (__int64)Block, 2u);
    v48 = std::operator<<<std::char_traits<char>>(v47, (__int64)" AS client FROM ");
    v49 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v49 = (_QWORD *)v107[0];
    v50 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v48, (__int64)v49, v108.m128i_u64[0]);
    v51 = std::operator<<<std::char_traits<char>>(v50, (__int64)" INNER JOIN ");
    v52 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v52 = *(_BYTE **)v102;
    v53 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v51, (__int64)v52, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v53, (__int64)" ON (");
    if ( v112.m128i_i64[1] > 0xFuLL )
    {
      v54 = Block[0];
      if ( (unsigned __int64)(v112.m128i_i64[1] + 1) >= 0x1000 )
      {
        v54 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v54 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v54);
    }
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v112 = v55;
    if ( v106.m128i_i64[1] > 0xFuLL )
    {
      v56 = v105[0];
      if ( (unsigned __int64)(v106.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v105[0] - 1);
        if ( (unsigned __int64)((char *)v105[0] - (char *)v56 - 8) > 0x1F )
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v68,
      16,
      (unsigned int)v107,
      (unsigned int)v102,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
    v69 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v70 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v70 = (_QWORD *)v107[0];
    v71 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v69, (__int64)v70, v108.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v71, (__int64)";");
    std::stringbuf::str(v100, a2);
    std::string::_Tidy_deallocate(v113);
    v113[0] = 19937;
    v114 = v55;
    std::string::_Tidy_deallocate(v102);
    *(_QWORD *)v102 = 19937;
    si128 = v55;
    std::string::_Tidy_deallocate(v107);
    v107[0] = 19937;
    v108 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::MapName(v105);
    v74 = v73[2];
    if ( v73[3] > 0xFu )
      v73 = (_QWORD *)*v73;
    v75 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v72, (__int64)v73, v74);
    std::operator<<<std::char_traits<char>>(v75, (__int64)";");
    std::string::_Tidy_deallocate(v105);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"PackageSources");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v105 = 0;
        v106 = 0;
        std::string::_Construct<1,char const *>(v105, "PackageSources", 0xEu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
          v90,
          4,
          (unsigned int)v105,
          (_DWORD)a1 + 448,
          (__int64)v98);
        std::string::_Tidy_deallocate(v105);
        std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x40u:
        v91 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"PackageSources");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"PackageSources");
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
    *(_OWORD *)v105 = 0;
    v106 = 0;
    std::string::_Construct<1,char const *>(v105, "PackageSources", 0xEu);
    v95(a1, v105);
    if ( v106.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v105, v105[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v105 = 0;
  v106 = 0;
  std::string::_Construct<1,char const *>(v105, "PackageSources", 0xEu);
  v76 = v105;
  v77 = 4;
LABEL_66:
  v109 = 0;
  v110 = 0;
  v109 = *(_OWORD *)v76;
  v110 = *((__m128i *)v76 + 1);
  *(_BYTE *)v76 = 0;
  v76[2] = 0;
  v76[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v105);
  }
  v78 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v112 = v78;
  }
  v79 = &v109;
  if ( v110.m128i_i64[1] > 0xFuLL )
    v79 = (__int128 *)v109;
  v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v99, (__int64)v79, v110.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v80, (__int64)"(");
  v81 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
    v82,
    a4,
    (unsigned int)&v109,
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v86,
      8,
      (unsigned int)&v109,
      v81,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
  std::stringbuf::str(v100, a2);
  std::string::_Tidy_deallocate(&v109);
  *(_QWORD *)&v109 = 19937;
  v110 = v78;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  v101[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
  return a2;
}

```

## disassembly

```asm
0x18006fdac  mov     rax, rsp
0x18006fdaf  mov     [rax+18h], rbx
0x18006fdb3  mov     [rax+20h], rsi
0x18006fdb7  push    rbp
0x18006fdb8  push    r12
0x18006fdba  push    r13
0x18006fdbc  push    r14
0x18006fdbe  push    r15
0x18006fdc0  lea     rbp, [rax-158h]
0x18006fdc7  sub     rsp, 230h
0x18006fdce  movaps  xmmword ptr [rax-38h], xmm6
0x18006fdd2  mov     rax, cs:__security_cookie
0x18006fdd9  xor     rax, rsp
0x18006fddc  mov     [rbp+150h+var_40], rax
0x18006fde3  movzx   esi, r9w
0x18006fde7  mov     r14, rdx
0x18006fdea  mov     r15, rcx
0x18006fded  mov     qword ptr [rsp+250h+var_218], rdx
0x18006fdf2  xor     r12d, r12d
0x18006fdf5  mov     [rsp+250h+var_210], r12d
0x18006fdfa  lea     rcx, [rsp+250h+var_200]
0x18006fdff  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18006fe04  nop
0x18006fe05  mov     eax, 800h
0x18006fe0a  cmp     ax, si
0x18006fe0d  jnz     loc_1800704E3
0x18006fe13  lea     rcx, [rbp+150h+var_C0]
0x18006fe1a  call    ?IndexName@?$Table@VPackageSources@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageSources@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::IndexName(void)
0x18006fe1f  nop
0x18006fe20  xorps   xmm0, xmm0
0x18006fe23  movups  [rbp+150h+var_100], xmm0
0x18006fe27  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000e
0x18006fe2f  movdqu  [rbp+150h+var_F0], xmm1
0x18006fe34  movsd   xmm0, qword ptr cs:aPackagesources; "PackageSources"
0x18006fe3c  movsd   qword ptr [rbp+150h+var_100], xmm0
0x18006fe41  mov     eax, dword ptr cs:aPackagesources+8; "ources"
0x18006fe47  mov     dword ptr [rbp+150h+var_100+8], eax
0x18006fe4a  movzx   eax, word ptr cs:aPackagesources+0Ch; "es"
0x18006fe51  mov     word ptr [rbp+150h+var_100+0Ch], ax
0x18006fe55  mov     byte ptr [rbp+150h+var_100+0Eh], r12b
0x18006fe59  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18006fe60  lea     rcx, [rsp+250h+var_1F0]
0x18006fe65  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006fe6a  lea     rdx, [rbp+150h+var_100]
0x18006fe6e  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006fe73  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18006fe78  mov     r8, qword ptr [rbp+150h+var_F0]
0x18006fe7c  mov     rcx, rax
0x18006fe7f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006fe84  lea     rdx, aSelectNull; " SELECT NULL"
0x18006fe8b  mov     rcx, rax
0x18006fe8e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006fe93  lea     r9, [r15+1C0h]
0x18006fe9a  mov     edx, 802h
0x18006fe9f  lea     rax, [rsp+250h+var_200]
0x18006fea4  mov     [rsp+250h+Reserved], rax
0x18006fea9  lea     r8, [rbp+150h+var_C0]
0x18006feb0  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18006feb5  lea     rdx, aFrom_0; " FROM "
0x18006febc  lea     rcx, [rsp+250h+var_1F0]
0x18006fec1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006fec6  lea     rdx, [rbp+150h+var_C0]
0x18006fecd  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x18006fed5  cmova   rdx, [rbp+150h+var_C0]
0x18006fedd  mov     r8, qword ptr [rbp+150h+var_B0]
0x18006fee4  mov     rcx, rax
0x18006fee7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006feec  lea     edx, [r12+10h]
0x18006fef1  lea     rax, [rsp+250h+var_200]
0x18006fef6  mov     [rsp+250h+Reserved], rax
0x18006fefb  lea     r9, [rbp+150h+var_100]
0x18006feff  lea     r8, [rbp+150h+var_C0]
0x18006ff06  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18006ff0b  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18006ff12  lea     rcx, [rsp+250h+var_1F0]
0x18006ff17  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ff1c  lea     rdx, [rbp+150h+var_100]
0x18006ff20  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006ff25  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18006ff2a  mov     r8, qword ptr [rbp+150h+var_F0]
0x18006ff2e  mov     rcx, rax
0x18006ff31  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ff36  lea     rdx, aOn; " ON ("
0x18006ff3d  mov     rcx, rax
0x18006ff40  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ff45  mov     rax, [r15+1E8h]
0x18006ff4c  mov     [rsp+250h+var_220], rax
0x18006ff51  mov     rsi, [r15+1E0h]
0x18006ff58  lea     r13d, [r12+40h]
0x18006ff5d  cmp     rsi, rax
0x18006ff60  jz      loc_180070000
0x18006ff66  lea     rbx, [rsi+38h]
0x18006ff6a  test    r12, r12
0x18006ff6d  jz      short loc_18006FF80
0x18006ff6f  lea     rdx, aAnd_1; " AND "
0x18006ff76  lea     rcx, [rsp+250h+var_1F0]
0x18006ff7b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ff80  lea     rdx, [rbp+150h+var_100]
0x18006ff84  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006ff89  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18006ff8e  mov     r8, qword ptr [rbp+150h+var_F0]
0x18006ff92  lea     rcx, [rsp+250h+var_1F0]
0x18006ff97  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ff9c  lea     rdx, asc_1801D0CE8; "."
0x18006ffa3  mov     rcx, rax
0x18006ffa6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ffab  mov     rdx, rsi
0x18006ffae  cmp     qword ptr [rbx-20h], 0Fh
0x18006ffb3  jbe     short loc_18006FFB8
0x18006ffb5  mov     rdx, [rsi]
0x18006ffb8  mov     r8, [rbx-28h]
0x18006ffbc  mov     rcx, rax
0x18006ffbf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ffc4  lea     rdx, asc_1801D5B8C; " = "
0x18006ffcb  mov     rcx, rax
0x18006ffce  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006ffd3  lea     rdx, [rbx-18h]
0x18006ffd7  cmp     qword ptr [rbx], 0Fh
0x18006ffdb  jbe     short loc_18006FFE0
0x18006ffdd  mov     rdx, [rdx]
0x18006ffe0  mov     r8, [rbx-8]
0x18006ffe4  mov     rcx, rax
0x18006ffe7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006ffec  inc     r12
0x18006ffef  add     rsi, r13
0x18006fff2  add     rbx, r13
0x18006fff5  cmp     rsi, [rsp+250h+var_220]
0x18006fffa  jnz     loc_18006FF6A
0x180070000  lea     rdx, aWhere; ") WHERE "
0x180070007  lea     rcx, [rsp+250h+var_1F0]
0x18007000c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070011  lea     rdx, [rbp+150h+var_100]
0x180070015  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18007001a  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18007001f  mov     r8, qword ptr [rbp+150h+var_F0]
0x180070023  mov     rcx, rax
0x180070026  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18007002b  lea     r12, asc_1801D0CE8; "."
0x180070032  mov     rdx, r12
0x180070035  mov     rcx, rax
0x180070038  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18007003d  nop
0x18007003e  xorps   xmm0, xmm0
0x180070041  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180070045  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x18007004d  movdqu  [rbp+150h+var_D0], xmm1
0x180070055  mov     esi, 6469h
0x18007005a  mov     word ptr [rbp+150h+var_E0], si
0x18007005e  mov     byte ptr [rbp+150h+var_E0+2], 0
0x180070062  mov     ebx, 2
0x180070067  mov     r8d, ebx
0x18007006a  lea     rdx, [rbp+150h+var_E0]
0x18007006e  mov     rcx, rax
0x180070071  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180070076  lea     rdx, aIsNull; " IS NULL;"
0x18007007d  mov     rcx, rax
0x180070080  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070085  nop
0x180070086  lea     rcx, [rbp+150h+var_E0]
0x18007008a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007008f  lea     rcx, [rbp+150h+var_60]
0x180070096  call    ?MapName@?$Table@VPackageSources@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageSources@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageSources,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>>::MapName(void)
0x18007009b  nop
0x18007009c  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x1800700a3  lea     rcx, [rsp+250h+var_1F0]
0x1800700a8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800700ad  lea     rdx, [rbp+150h+var_60]
0x1800700b4  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x1800700bc  cmova   rdx, [rbp+150h+var_60]
0x1800700c4  mov     r8, qword ptr [rbp+150h+var_50]
0x1800700cb  mov     rcx, rax
0x1800700ce  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800700d3  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x1800700da  mov     rcx, rax
0x1800700dd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800700e2  lea     rdx, aInsertInto; "INSERT INTO "
0x1800700e9  lea     rcx, [rsp+250h+var_1F0]
0x1800700ee  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800700f3  lea     rdx, [rbp+150h+var_60]
0x1800700fa  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x180070102  cmova   rdx, [rbp+150h+var_60]
0x18007010a  mov     r8, qword ptr [rbp+150h+var_50]
0x180070111  mov     rcx, rax
0x180070114  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180070119  lea     rdx, aSelect; " SELECT "
0x180070120  mov     rcx, rax
0x180070123  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070128  lea     rdx, [rbp+150h+var_C0]
0x18007012f  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180070137  cmova   rdx, [rbp+150h+var_C0]
0x18007013f  mov     r8, qword ptr [rbp+150h+var_B0]
0x180070146  mov     rcx, rax
0x180070149  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18007014e  mov     rdx, r12
0x180070151  mov     rcx, rax
0x180070154  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070159  nop
0x18007015a  xorps   xmm0, xmm0
0x18007015d  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180070161  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180070169  movdqu  [rbp+150h+var_D0], xmm1
0x180070171  mov     word ptr [rbp+150h+var_E0], si
0x180070175  mov     byte ptr [rbp+150h+var_E0+2], 0
0x180070179  mov     r8d, ebx
0x18007017c  lea     rdx, [rbp+150h+var_E0]
0x180070180  mov     rcx, rax
0x180070183  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180070188  lea     rdx, aAsIncoming; " AS incoming, "
0x18007018f  mov     rcx, rax
0x180070192  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070197  lea     rdx, [rbp+150h+var_100]
0x18007019b  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x1800701a0  cmova   rdx, qword ptr [rbp+150h+var_100]
0x1800701a5  mov     r8, qword ptr [rbp+150h+var_F0]
0x1800701a9  mov     rcx, rax
0x1800701ac  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800701b1  mov     rdx, r12
0x1800701b4  mov     rcx, rax
0x1800701b7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800701bc  nop
0x1800701bd  xorps   xmm0, xmm0
0x1800701c0  movups  xmmword ptr [rbp+150h+Block], xmm0
0x1800701c7  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x1800701cf  movdqu  [rbp+150h+var_70], xmm1
0x1800701d7  mov     word ptr [rbp+150h+Block], si
0x1800701de  xor     esi, esi
0x1800701e0  mov     byte ptr [rbp+150h+Block+2], sil
0x1800701e7  mov     r8d, ebx
0x1800701ea  lea     rdx, [rbp+150h+Block]
0x1800701f1  mov     rcx, rax
0x1800701f4  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800701f9  lea     rdx, aAsClientFrom; " AS client FROM "
0x180070200  mov     rcx, rax
0x180070203  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070208  lea     rdx, [rbp+150h+var_C0]
0x18007020f  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180070217  cmova   rdx, [rbp+150h+var_C0]
0x18007021f  mov     r8, qword ptr [rbp+150h+var_B0]
0x180070226  mov     rcx, rax
0x180070229  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18007022e  lea     rdx, aInnerJoin; " INNER JOIN "
0x180070235  mov     rcx, rax
0x180070238  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18007023d  lea     rdx, [rbp+150h+var_100]
0x180070241  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180070246  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18007024b  mov     r8, qword ptr [rbp+150h+var_F0]
0x18007024f  mov     rcx, rax
0x180070252  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180070257  lea     rdx, aOn; " ON ("
0x18007025e  mov     rcx, rax
0x180070261  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180070266  nop
0x180070267  mov     ebx, 1000h
0x18007026c  mov     rax, qword ptr [rbp+150h+var_70+8]
0x180070273  cmp     rax, 0Fh
0x180070277  jbe     short loc_1800702B8
0x180070279  mov     rcx, [rbp+150h+Block]; Block
0x180070280  mov     rdx, rcx
0x180070283  inc     rax
0x180070286  cmp     rax, rbx
0x180070289  jb      short loc_1800702B2
0x18007028b  mov     rcx, [rcx-8]
0x18007028f  sub     rdx, rcx
0x180070292  lea     rax, [rdx-8]
0x180070296  cmp     rax, 1Fh
0x18007029a  jbe     short loc_1800702B2
0x18007029c  mov     [rsp+250h+Reserved], rsi; Reserved
0x1800702a1  xor     r9d, r9d; LineNo
0x1800702a4  xor     r8d, r8d; FileName
0x1800702a7  xor     edx, edx; FunctionName
0x1800702a9  xor     ecx, ecx; Expression
0x1800702ab  call    cs:__imp__invoke_watson
0x1800702b2  call    cs:__imp_free
0x1800702b8  mov     r12d, 4DE1h
0x1800702be  mov     [rbp+150h+Block], r12
0x1800702c5  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800702cd  movdqu  [rbp+150h+var_70], xmm6
0x1800702d5  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x1800702dc  cmp     rax, 0Fh
0x1800702e0  jbe     short loc_18007031E
0x1800702e2  mov     rcx, [rbp+150h+var_E0]; Block
0x1800702e6  mov     rdx, rcx
0x1800702e9  inc     rax
0x1800702ec  cmp     rax, rbx
0x1800702ef  jb      short loc_180070318
0x1800702f1  mov     rcx, [rcx-8]
0x1800702f5  sub     rdx, rcx
0x1800702f8  lea     rax, [rdx-8]
0x1800702fc  cmp     rax, 1Fh
0x180070300  jbe     short loc_180070318
0x180070302  mov     [rsp+250h+Reserved], rsi; Reserved
0x180070307  xor     r9d, r9d; LineNo
0x18007030a  xor     r8d, r8d; FileName
0x18007030d  xor     edx, edx; FunctionName
0x18007030f  xor     ecx, ecx; Expression
0x180070311  call    cs:__imp__invoke_watson
0x180070318  call    cs:__imp_free
0x18007031e  mov     rax, rsi
0x180070321  mov     [rsp+250h+var_220], rax
  ... truncated ...
```
