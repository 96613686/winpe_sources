# RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18005f710`
- end: `0x180060457`
- name: `?CreateText@?$Table@VDirectories@Tables@Meta@RepoMan@@V?$TablePolicy@UDirectories@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3399`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e49c`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18005e828`
- `0x18005f710`
- `0x180060458`
- `0x180062108`
- `0x18006216c`
- `0x180065ed0`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fa87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fd05`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fa87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fd05`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005fa80`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005fcfe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005fa80`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005fcfe`

## string_xrefs

- `0x18005f9f7`: `directory_id`
- `0x18005fb75`: `directory_id`
- `0x18005fbf3`: `directory_id`
- `0x18005fad1`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18005fa9a`: `CREATE TABLE IF NOT EXISTS `
- `0x1800603b7`: `CREATE TABLE IF NOT EXISTS `
- `0x18005fb9e`: ` AS incoming, `
- `0x18005ffd3`: `REPLACE INTO `
- `0x18006021b`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::CreateText(
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
  _BYTE v105[10]; // [rsp+158h] [rbp+50h] BYREF
  int v106; // [rsp+162h] [rbp+5Ah]
  __int16 v107; // [rsp+166h] [rbp+5Eh]
  __m128i v108; // [rsp+168h] [rbp+60h]
  void *v109[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v110; // [rsp+188h] [rbp+80h]
  _QWORD v111[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v112; // [rsp+1A8h] [rbp+A0h]
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v114; // [rsp+1C8h] [rbp+C0h]
  __int128 v115; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v116; // [rsp+1E8h] [rbp+E0h]
  _QWORD v117[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v118; // [rsp+208h] [rbp+100h]
  __int128 v119; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int64 v121; // [rsp+238h] [rbp+130h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  if ( a4 == 2048 )
  {
    v119 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v119) = 0;
    v121 = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::IndexName(v111);
    v107 = 0;
    v108 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v105, "Directorie", sizeof(v105));
    v106 = (unsigned __int8)aDirectories[10];
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = v105;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v8 = *(_BYTE **)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v108.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(
      v10,
      2050,
      (unsigned int)v111,
      (_DWORD)a1 + 448,
      (__int64)v101);
    v11 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" FROM ");
    v12 = v111;
    if ( v112.m128i_i64[1] > 0xFuLL )
      v12 = (_QWORD *)v111[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, (__int64)v12, v112.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v111,
      (unsigned int)v105,
      (__int64)v101);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" LEFT OUTER JOIN ");
    v15 = v105;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v15 = *(_BYTE **)v105;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v108.m128i_u64[0]);
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
        if ( v108.m128i_i64[1] > 0xFuLL )
          v20 = *(_BYTE **)v105;
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v20,
                v108.m128i_u64[0]);
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
    if ( v108.m128i_i64[1] > 0xFuLL )
      v28 = *(_BYTE **)v105;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v108.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v114 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"directory_id";
    Block[1] = (void *)*(unsigned int *)"y_id";
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 0xCu);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    if ( v114.m128i_i64[1] > 0xFuLL )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(v114.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::MapName(v117);
    v33 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v34 = v117;
    if ( v118.m128i_i64[1] > 0xFuLL )
      v34 = (_QWORD *)v117[0];
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, (__int64)v34, v118.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v35,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v36 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"INSERT INTO ");
    v37 = v117;
    if ( v118.m128i_i64[1] > 0xFuLL )
      v37 = (_QWORD *)v117[0];
    v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, (__int64)v37, v118.m128i_u64[0]);
    v39 = std::operator<<<std::char_traits<char>>(v38, (__int64)" SELECT ");
    v40 = v111;
    if ( v112.m128i_i64[1] > 0xFuLL )
      v40 = (_QWORD *)v111[0];
    v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, (__int64)v40, v112.m128i_u64[0]);
    v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)".");
    v110 = _mm_load_si128((const __m128i *)&_xmm);
    v109[0] = *(void **)"directory_id";
    v109[1] = (void *)*(unsigned int *)"y_id";
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v109, 0xCu);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = v105;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v45 = *(_BYTE **)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v108.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v114 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"directory_id";
    Block[1] = (void *)*(unsigned int *)"y_id";
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 0xCu);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v111;
    if ( v112.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v111[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v112.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = v105;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v53 = *(_BYTE **)v105;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, v108.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v54, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v114 = v55;
    if ( v110.m128i_i64[1] > 0xFuLL )
    {
      v56 = v109[0];
      if ( (unsigned __int64)(v110.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v109[0] - 1);
        if ( (unsigned __int64)((char *)v109[0] - (char *)v56 - 8) > 0x1F )
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
        if ( v108.m128i_i64[1] > 0xFuLL )
          v61 = *(_BYTE **)v105;
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v61,
                v108.m128i_u64[0]);
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
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>::BuildText(
      v68,
      0,
      144,
      (unsigned int)v111,
      (__int64)v105,
      (__int64)v101);
    RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>::BuildText(
      v69,
      1,
      784,
      (unsigned int)v111,
      Reserved,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
    v70 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v71 = v111;
    if ( v112.m128i_i64[1] > 0xFuLL )
      v71 = (_QWORD *)v111[0];
    v72 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v70, (__int64)v71, v112.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v72, (__int64)";");
    std::stringbuf::str(v103, a2);
    std::string::_Tidy_deallocate(v117);
    v117[0] = 19937;
    v118 = v55;
    std::string::_Tidy_deallocate(v105);
    *(_QWORD *)v105 = 19937;
    v108 = v55;
    std::string::_Tidy_deallocate(v111);
    v111[0] = 19937;
    v112 = v55;
    std::string::_Tidy_deallocate(&v119);
    *(_QWORD *)&v119 = 19937;
    si128 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
    v104[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v73 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::MapName(v109);
    v75 = v74[2];
    if ( v74[3] > 0xFu )
      v74 = (_QWORD *)*v74;
    v76 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v73, (__int64)v74, v75);
    std::operator<<<std::char_traits<char>>(v76, (__int64)";");
    std::string::_Tidy_deallocate(v109);
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
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Directories");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v109 = 0;
        v110 = 0;
        std::string::_Construct<1,char const *>(v109, "Directories", 0xBu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(
          v91,
          4,
          (unsigned int)v109,
          (_DWORD)a1 + 448,
          (__int64)v101);
        std::string::_Tidy_deallocate(v109);
        std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x40u:
        v92 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Directories");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Directories");
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
    *(_OWORD *)v109 = 0;
    v110 = 0;
    std::string::_Construct<1,char const *>(v109, "Directories", 0xBu);
    v96(a1, v109);
    if ( v110.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v109, v109[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v109 = 0;
  v110 = 0;
  std::string::_Construct<1,char const *>(v109, "Directories", 0xBu);
  v78 = v109;
  v77 = 4;
LABEL_66:
  v115 = 0;
  v116 = 0;
  v115 = *(_OWORD *)v78;
  v116 = *((__m128i *)v78 + 1);
  *(_BYTE *)v78 = 0;
  v78[2] = 0;
  v78[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v109);
  }
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v114 = v79;
  }
  v80 = &v115;
  if ( v116.m128i_i64[1] > 0xFuLL )
    v80 = (__int128 *)v115;
  v81 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
          (__int64)v102,
          (__int64)v80,
          v116.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v81, (__int64)"(");
  v82 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(
    v83,
    a4,
    (unsigned int)&v115,
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(
      v87,
      8,
      (unsigned int)&v115,
      v82,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
  std::stringbuf::str(v103, a2);
  std::string::_Tidy_deallocate(&v115);
  *(_QWORD *)&v115 = 19937;
  v116 = v79;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
  v104[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
  return a2;
}

```

## disassembly

```asm
0x18005f710  mov     rax, rsp
0x18005f713  mov     [rax+18h], rbx
0x18005f717  mov     [rax+20h], rsi
0x18005f71b  push    rbp
0x18005f71c  push    r12
0x18005f71e  push    r13
0x18005f720  push    r14
0x18005f722  push    r15
0x18005f724  lea     rbp, [rax-178h]
0x18005f72b  sub     rsp, 250h
0x18005f732  movaps  xmmword ptr [rax-38h], xmm6
0x18005f736  mov     rax, cs:__security_cookie
0x18005f73d  xor     rax, rsp
0x18005f740  mov     [rbp+170h+var_38], rax
0x18005f747  movzx   esi, r9w
0x18005f74b  mov     r14, rdx
0x18005f74e  mov     r15, rcx
0x18005f751  mov     [rsp+270h+var_238], rdx
0x18005f756  xor     r13d, r13d
0x18005f759  mov     [rsp+270h+var_230], r13d
0x18005f75e  lea     rcx, [rsp+270h+var_220]
0x18005f763  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18005f768  nop
0x18005f769  mov     eax, 800h
0x18005f76e  cmp     ax, si
0x18005f771  jnz     loc_18005FF16
0x18005f777  xorps   xmm0, xmm0
0x18005f77a  movups  [rbp+170h+var_60], xmm0
0x18005f781  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18005f789  movdqu  [rbp+170h+var_50], xmm1
0x18005f791  mov     byte ptr [rbp+170h+var_60], r13b
0x18005f798  mov     [rbp+170h+var_40], r13
0x18005f79f  lea     rcx, [rbp+170h+var_E0]
0x18005f7a6  call    ?IndexName@?$Table@VDirectories@Tables@Meta@RepoMan@@V?$TablePolicy@UDirectories@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::IndexName(void)
0x18005f7ab  nop
0x18005f7ac  xorps   xmm0, xmm0
0x18005f7af  movups  [rbp+170h+var_120], xmm0
0x18005f7b3  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000b
0x18005f7bb  movdqu  [rbp+170h+var_110], xmm1
0x18005f7c0  movsd   xmm0, qword ptr cs:aDirectories; "Directories"
0x18005f7c8  movsd   qword ptr [rbp+170h+var_120], xmm0
0x18005f7cd  movzx   eax, word ptr cs:aDirectories+8; "ies"
0x18005f7d4  mov     word ptr [rbp+170h+var_120+8], ax
0x18005f7d8  mov     al, byte ptr cs:aDirectories+0Ah; "s"
0x18005f7de  mov     byte ptr [rbp+170h+var_120+0Ah], al
0x18005f7e1  mov     byte ptr [rbp+170h+var_120+0Bh], r13b
0x18005f7e5  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18005f7ec  lea     rcx, [rsp+270h+var_210]
0x18005f7f1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f7f6  lea     rdx, [rbp+170h+var_120]
0x18005f7fa  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005f7ff  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005f804  mov     r8, qword ptr [rbp+170h+var_110]
0x18005f808  mov     rcx, rax
0x18005f80b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f810  lea     rdx, aSelectNull; " SELECT NULL"
0x18005f817  mov     rcx, rax
0x18005f81a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f81f  lea     r9, [r15+1C0h]
0x18005f826  mov     edx, 802h
0x18005f82b  lea     rax, [rsp+270h+var_220]
0x18005f830  mov     [rsp+270h+Reserved], rax
0x18005f835  lea     r8, [rbp+170h+var_E0]
0x18005f83c  call    ?BuildText@?$RowType@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18005f841  lea     rdx, aFrom_0; " FROM "
0x18005f848  lea     rcx, [rsp+270h+var_210]
0x18005f84d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f852  lea     rdx, [rbp+170h+var_E0]
0x18005f859  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005f861  cmova   rdx, [rbp+170h+var_E0]
0x18005f869  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005f870  mov     rcx, rax
0x18005f873  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f878  lea     edx, [r13+10h]
0x18005f87c  lea     rax, [rsp+270h+var_220]
0x18005f881  mov     [rsp+270h+Reserved], rax
0x18005f886  lea     r9, [rbp+170h+var_120]
0x18005f88a  lea     r8, [rbp+170h+var_E0]
0x18005f891  call    ?BuildText@?$RowType@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18005f896  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18005f89d  lea     rcx, [rsp+270h+var_210]
0x18005f8a2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f8a7  lea     rdx, [rbp+170h+var_120]
0x18005f8ab  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005f8b0  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005f8b5  mov     r8, qword ptr [rbp+170h+var_110]
0x18005f8b9  mov     rcx, rax
0x18005f8bc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f8c1  lea     rdx, aOn; " ON ("
0x18005f8c8  mov     rcx, rax
0x18005f8cb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f8d0  mov     eax, r13d
0x18005f8d3  mov     [rsp+270h+var_240], rax
0x18005f8d8  mov     rcx, [r15+1E8h]
0x18005f8df  mov     [rsp+270h+var_238], rcx
0x18005f8e4  mov     rsi, [r15+1E0h]
0x18005f8eb  lea     r12d, [r13+1]
0x18005f8ef  lea     r13d, [rax+40h]
0x18005f8f3  cmp     rsi, rcx
0x18005f8f6  jz      loc_18005F9A0
0x18005f8fc  lea     rbx, [rsi+38h]
0x18005f900  test    rax, rax
0x18005f903  jz      short loc_18005F916
0x18005f905  lea     rdx, aAnd_1; " AND "
0x18005f90c  lea     rcx, [rsp+270h+var_210]
0x18005f911  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f916  lea     rdx, [rbp+170h+var_120]
0x18005f91a  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005f91f  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005f924  mov     r8, qword ptr [rbp+170h+var_110]
0x18005f928  lea     rcx, [rsp+270h+var_210]
0x18005f92d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f932  lea     rdx, asc_1801D0CE8; "."
0x18005f939  mov     rcx, rax
0x18005f93c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f941  mov     rdx, rsi
0x18005f944  cmp     qword ptr [rbx-20h], 0Fh
0x18005f949  jbe     short loc_18005F94E
0x18005f94b  mov     rdx, [rsi]
0x18005f94e  mov     r8, [rbx-28h]
0x18005f952  mov     rcx, rax
0x18005f955  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f95a  lea     rdx, asc_1801D5B8C; " = "
0x18005f961  mov     rcx, rax
0x18005f964  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f969  lea     rdx, [rbx-18h]
0x18005f96d  cmp     qword ptr [rbx], 0Fh
0x18005f971  jbe     short loc_18005F976
0x18005f973  mov     rdx, [rdx]
0x18005f976  mov     r8, [rbx-8]
0x18005f97a  mov     rcx, rax
0x18005f97d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f982  mov     rax, [rsp+270h+var_240]
0x18005f987  add     rax, r12
0x18005f98a  mov     [rsp+270h+var_240], rax
0x18005f98f  add     rsi, r13
0x18005f992  add     rbx, r13
0x18005f995  cmp     rsi, [rsp+270h+var_238]
0x18005f99a  jnz     loc_18005F900
0x18005f9a0  lea     rdx, aWhere; ") WHERE "
0x18005f9a7  lea     rcx, [rsp+270h+var_210]
0x18005f9ac  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f9b1  lea     rdx, [rbp+170h+var_120]
0x18005f9b5  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005f9ba  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005f9bf  mov     r8, qword ptr [rbp+170h+var_110]
0x18005f9c3  mov     rcx, rax
0x18005f9c6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005f9cb  lea     rdx, asc_1801D0CE8; "."
0x18005f9d2  mov     rcx, rax
0x18005f9d5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005f9da  mov     rcx, rax
0x18005f9dd  xorps   xmm0, xmm0
0x18005f9e0  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18005f9e7  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x18005f9ef  movdqu  [rbp+170h+var_B0], xmm1
0x18005f9f7  movsd   xmm0, qword ptr cs:aDirectoryId; "directory_id"
0x18005f9ff  movsd   [rbp+170h+Block], xmm0
0x18005fa07  mov     eax, dword ptr cs:aDirectoryId+8; "y_id"
0x18005fa0d  mov     dword ptr [rbp+170h+Block+8], eax
0x18005fa13  xor     esi, esi
0x18005fa15  mov     byte ptr [rbp+170h+Block+0Ch], sil
0x18005fa1c  lea     r8d, [rsi+0Ch]
0x18005fa20  lea     rdx, [rbp+170h+Block]
0x18005fa27  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fa2c  lea     rdx, aIsNull; " IS NULL;"
0x18005fa33  mov     rcx, rax
0x18005fa36  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fa3b  nop
0x18005fa3c  mov     ebx, 1000h
0x18005fa41  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18005fa48  cmp     rax, 0Fh
0x18005fa4c  jbe     short loc_18005FA8D
0x18005fa4e  mov     rcx, [rbp+170h+Block]; Block
0x18005fa55  mov     rdx, rcx
0x18005fa58  inc     rax
0x18005fa5b  cmp     rax, rbx
0x18005fa5e  jb      short loc_18005FA87
0x18005fa60  mov     rcx, [rcx-8]
0x18005fa64  sub     rdx, rcx
0x18005fa67  lea     rax, [rdx-8]
0x18005fa6b  cmp     rax, 1Fh
0x18005fa6f  jbe     short loc_18005FA87
0x18005fa71  mov     [rsp+270h+Reserved], rsi; Reserved
0x18005fa76  xor     r9d, r9d; LineNo
0x18005fa79  xor     r8d, r8d; FileName
0x18005fa7c  xor     edx, edx; FunctionName
0x18005fa7e  xor     ecx, ecx; Expression
0x18005fa80  call    cs:__imp__invoke_watson
0x18005fa87  call    cs:__imp_free
0x18005fa8d  lea     rcx, [rbp+170h+var_80]
0x18005fa94  call    ?MapName@?$Table@VDirectories@Tables@Meta@RepoMan@@V?$TablePolicy@UDirectories@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Directories,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Directories,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::MapName(void)
0x18005fa99  nop
0x18005fa9a  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18005faa1  lea     rcx, [rsp+270h+var_210]
0x18005faa6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005faab  lea     rdx, [rbp+170h+var_80]
0x18005fab2  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18005faba  cmova   rdx, [rbp+170h+var_80]
0x18005fac2  mov     r8, qword ptr [rbp+170h+var_70]
0x18005fac9  mov     rcx, rax
0x18005facc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fad1  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x18005fad8  mov     rcx, rax
0x18005fadb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fae0  lea     rdx, aInsertInto; "INSERT INTO "
0x18005fae7  lea     rcx, [rsp+270h+var_210]
0x18005faec  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005faf1  lea     rdx, [rbp+170h+var_80]
0x18005faf8  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18005fb00  cmova   rdx, [rbp+170h+var_80]
0x18005fb08  mov     r8, qword ptr [rbp+170h+var_70]
0x18005fb0f  mov     rcx, rax
0x18005fb12  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fb17  lea     rdx, aSelect; " SELECT "
0x18005fb1e  mov     rcx, rax
0x18005fb21  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fb26  lea     rdx, [rbp+170h+var_E0]
0x18005fb2d  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005fb35  cmova   rdx, [rbp+170h+var_E0]
0x18005fb3d  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005fb44  mov     rcx, rax
0x18005fb47  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fb4c  lea     rdx, asc_1801D0CE8; "."
0x18005fb53  mov     rcx, rax
0x18005fb56  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fb5b  mov     rcx, rax
0x18005fb5e  xorps   xmm0, xmm0
0x18005fb61  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18005fb65  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x18005fb6d  movdqu  [rbp+170h+var_F0], xmm1
0x18005fb75  movsd   xmm0, qword ptr cs:aDirectoryId; "directory_id"
0x18005fb7d  movsd   [rbp+170h+var_100], xmm0
0x18005fb82  mov     eax, dword ptr cs:aDirectoryId+8; "y_id"
0x18005fb88  mov     dword ptr [rbp+170h+var_100+8], eax
0x18005fb8b  mov     byte ptr [rbp+170h+var_100+0Ch], sil
0x18005fb8f  mov     r8d, 0Ch
0x18005fb95  lea     rdx, [rbp+170h+var_100]
0x18005fb99  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fb9e  lea     rdx, aAsIncoming; " AS incoming, "
0x18005fba5  mov     rcx, rax
0x18005fba8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fbad  lea     rdx, [rbp+170h+var_120]
0x18005fbb1  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005fbb6  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005fbbb  mov     r8, qword ptr [rbp+170h+var_110]
0x18005fbbf  mov     rcx, rax
0x18005fbc2  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fbc7  lea     rdx, asc_1801D0CE8; "."
0x18005fbce  mov     rcx, rax
0x18005fbd1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fbd6  mov     rcx, rax
0x18005fbd9  xorps   xmm0, xmm0
0x18005fbdc  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18005fbe3  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x18005fbeb  movdqu  [rbp+170h+var_B0], xmm1
0x18005fbf3  movsd   xmm0, qword ptr cs:aDirectoryId; "directory_id"
0x18005fbfb  movsd   [rbp+170h+Block], xmm0
0x18005fc03  mov     eax, dword ptr cs:aDirectoryId+8; "y_id"
0x18005fc09  mov     dword ptr [rbp+170h+Block+8], eax
0x18005fc0f  mov     byte ptr [rbp+170h+Block+0Ch], sil
0x18005fc16  mov     r8d, 0Ch
0x18005fc1c  lea     rdx, [rbp+170h+Block]
0x18005fc23  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fc28  lea     rdx, aAsClientFrom; " AS client FROM "
0x18005fc2f  mov     rcx, rax
0x18005fc32  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fc37  lea     rdx, [rbp+170h+var_E0]
0x18005fc3e  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005fc46  cmova   rdx, [rbp+170h+var_E0]
0x18005fc4e  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005fc55  mov     rcx, rax
0x18005fc58  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fc5d  lea     rdx, aInnerJoin; " INNER JOIN "
0x18005fc64  mov     rcx, rax
0x18005fc67  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fc6c  lea     rdx, [rbp+170h+var_120]
0x18005fc70  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005fc75  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005fc7a  mov     r8, qword ptr [rbp+170h+var_110]
0x18005fc7e  mov     rcx, rax
0x18005fc81  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005fc86  lea     rdx, aOn; " ON ("
0x18005fc8d  mov     rcx, rax
0x18005fc90  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005fc95  nop
0x18005fc96  lea     rcx, [rbp+170h+Block]
0x18005fc9d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005fca2  mov     esi, 4DE1h
0x18005fca7  mov     [rbp+170h+Block], rsi
0x18005fcae  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18005fcb6  movdqu  [rbp+170h+var_B0], xmm6
0x18005fcbe  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x18005fcc5  cmp     rax, 0Fh
0x18005fcc9  jbe     short loc_18005FD0B
0x18005fccb  mov     rcx, [rbp+170h+var_100]; Block
0x18005fccf  mov     rdx, rcx
0x18005fcd2  inc     rax
0x18005fcd5  cmp     rax, rbx
0x18005fcd8  jb      short loc_18005FD05
  ... truncated ...
```
