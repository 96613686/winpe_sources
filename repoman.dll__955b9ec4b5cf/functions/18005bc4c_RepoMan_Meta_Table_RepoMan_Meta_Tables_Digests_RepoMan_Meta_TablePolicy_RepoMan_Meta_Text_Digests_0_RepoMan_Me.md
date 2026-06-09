# RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18005bc4c`
- end: `0x18005c93f`
- name: `?CreateText@?$Table@VDigests@Tables@Meta@RepoMan@@V?$TablePolicy@UDigests@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3315`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059828`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x180059bb4`
- `0x18005bc4c`
- `0x18005e21c`
- `0x18005e394`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005bfb1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c224`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005bfb1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c224`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005bfaa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c21d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005bfaa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c21d`

## string_xrefs

- `0x18005bffb`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18005bfc4`: `CREATE TABLE IF NOT EXISTS `
- `0x18005c89f`: `CREATE TABLE IF NOT EXISTS `
- `0x18005c0c4`: ` AS incoming, `
- `0x18005c4cc`: `REPLACE INTO `
- `0x18005c713`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
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
  __int64 v17; // r12
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
  _BYTE v102[14]; // [rsp+158h] [rbp+50h] BYREF
  __int16 v103; // [rsp+166h] [rbp+5Eh]
  __m128i v104; // [rsp+168h] [rbp+60h]
  void *v105[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v106; // [rsp+188h] [rbp+80h]
  _QWORD v107[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v108; // [rsp+1A8h] [rbp+A0h]
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v110; // [rsp+1C8h] [rbp+C0h]
  __int128 v111; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v112; // [rsp+1E8h] [rbp+E0h]
  _QWORD v113[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v114; // [rsp+208h] [rbp+100h]
  __int128 v115; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int64 v117; // [rsp+238h] [rbp+130h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    v115 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v115) = 0;
    v117 = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v107);
    v103 = 0;
    v104 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v102, "Digest", 6);
    *(_QWORD *)&v102[6] = (unsigned __int8)aDigests[6];
    v7 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v8 = v102;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v8 = *(_BYTE **)v102;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v104.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v10,
      2050,
      (unsigned int)v107,
      (_DWORD)a1 + 448,
      (__int64)v98);
    v11 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" FROM ");
    v12 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v12 = (_QWORD *)v107[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, (__int64)v12, v108.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v107,
      (unsigned int)v102,
      (__int64)v98);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" LEFT OUTER JOIN ");
    v15 = v102;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v15 = *(_BYTE **)v102;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v104.m128i_u64[0]);
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
        v20 = v102;
        if ( v104.m128i_i64[1] > 0xFuLL )
          v20 = *(_BYTE **)v102;
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v20,
                v104.m128i_u64[0]);
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
    v28 = v102;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v28 = *(_BYTE **)v102;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v104.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v110 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"digest_id";
    Block[1] = (void *)(unsigned __int8)aDigestId[8];
    BYTE1(Block[1]) = 0;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 9u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    if ( v110.m128i_i64[1] > 0xFuLL )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(v110.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v113);
    v33 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v34 = v113;
    if ( v114.m128i_i64[1] > 0xFuLL )
      v34 = (_QWORD *)v113[0];
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, (__int64)v34, v114.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v35,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v36 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"INSERT INTO ");
    v37 = v113;
    if ( v114.m128i_i64[1] > 0xFuLL )
      v37 = (_QWORD *)v113[0];
    v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, (__int64)v37, v114.m128i_u64[0]);
    v39 = std::operator<<<std::char_traits<char>>(v38, (__int64)" SELECT ");
    v40 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v40 = (_QWORD *)v107[0];
    v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, (__int64)v40, v108.m128i_u64[0]);
    v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)".");
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    v105[0] = *(void **)"digest_id";
    v105[1] = (void *)(unsigned __int8)aDigestId[8];
    BYTE1(v105[1]) = 0;
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v105, 9u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = v102;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v45 = *(_BYTE **)v102;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v104.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v110 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"digest_id";
    Block[1] = (void *)(unsigned __int8)aDigestId[8];
    BYTE1(Block[1]) = 0;
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 9u);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v107;
    if ( v108.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v107[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v108.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = v102;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v53 = *(_BYTE **)v102;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, v104.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v54, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v110 = v55;
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
        if ( v104.m128i_i64[1] > 0xFuLL )
          v61 = *(_BYTE **)v102;
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v61,
                v104.m128i_u64[0]);
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    v104 = v55;
    std::string::_Tidy_deallocate(v107);
    v107[0] = 19937;
    v108 = v55;
    std::string::_Tidy_deallocate(&v115);
    *(_QWORD *)&v115 = 19937;
    si128 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v105);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"Digests");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v105 = 0;
        v106 = 0;
        std::string::_Construct<1,char const *>(v105, "Digests", 7u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"Digests");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"Digests");
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
    std::string::_Construct<1,char const *>(v105, "Digests", 7u);
    v95(a1, v105);
    if ( v106.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v105, v105[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v105 = 0;
  v106 = 0;
  std::string::_Construct<1,char const *>(v105, "Digests", 7u);
  v76 = v105;
  v77 = 4;
LABEL_66:
  v111 = 0;
  v112 = 0;
  v111 = *(_OWORD *)v76;
  v112 = *((__m128i *)v76 + 1);
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
    v110 = v78;
  }
  v79 = &v111;
  if ( v112.m128i_i64[1] > 0xFuLL )
    v79 = (__int128 *)v111;
  v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v99, (__int64)v79, v112.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v80, (__int64)"(");
  v81 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
    v82,
    a4,
    (unsigned int)&v111,
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v86,
      8,
      (unsigned int)&v111,
      v81,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
  std::stringbuf::str(v100, a2);
  std::string::_Tidy_deallocate(&v111);
  *(_QWORD *)&v111 = 19937;
  v112 = v78;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  v101[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
  return a2;
}

```

## disassembly

```asm
0x18005bc4c  mov     rax, rsp
0x18005bc4f  mov     [rax+18h], rbx
0x18005bc53  mov     [rax+20h], rsi
0x18005bc57  push    rbp
0x18005bc58  push    r12
0x18005bc5a  push    r13
0x18005bc5c  push    r14
0x18005bc5e  push    r15
0x18005bc60  lea     rbp, [rax-178h]
0x18005bc67  sub     rsp, 250h
0x18005bc6e  movaps  xmmword ptr [rax-38h], xmm6
0x18005bc72  mov     rax, cs:__security_cookie
0x18005bc79  xor     rax, rsp
0x18005bc7c  mov     [rbp+170h+var_38], rax
0x18005bc83  movzx   esi, r9w
0x18005bc87  mov     r14, rdx
0x18005bc8a  mov     r15, rcx
0x18005bc8d  mov     qword ptr [rsp+270h+var_238], rdx
0x18005bc92  xor     r13d, r13d
0x18005bc95  mov     [rsp+270h+var_230], r13d
0x18005bc9a  lea     rcx, [rsp+270h+var_220]
0x18005bc9f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18005bca4  nop
0x18005bca5  mov     eax, 800h
0x18005bcaa  cmp     ax, si
0x18005bcad  jnz     loc_18005C40A
0x18005bcb3  xorps   xmm0, xmm0
0x18005bcb6  movups  [rbp+170h+var_60], xmm0
0x18005bcbd  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18005bcc5  movdqu  [rbp+170h+var_50], xmm1
0x18005bccd  mov     byte ptr [rbp+170h+var_60], r13b
0x18005bcd4  mov     [rbp+170h+var_40], r13
0x18005bcdb  lea     rcx, [rbp+170h+var_E0]
0x18005bce2  call    ?IndexName@?$Table@VDigests@Tables@Meta@RepoMan@@V?$TablePolicy@UDigests@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x18005bce7  nop
0x18005bce8  xorps   xmm0, xmm0
0x18005bceb  movups  [rbp+170h+var_120], xmm0
0x18005bcef  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x18005bcf7  movdqu  [rbp+170h+var_110], xmm1
0x18005bcfc  mov     rax, qword ptr cs:aDigests; "Digests"
0x18005bd03  mov     dword ptr [rbp+170h+var_120], eax
0x18005bd06  movzx   eax, word ptr cs:aDigests+4; "sts"
0x18005bd0d  mov     word ptr [rbp+170h+var_120+4], ax
0x18005bd11  mov     al, byte ptr cs:aDigests+6; "s"
0x18005bd17  mov     byte ptr [rbp+170h+var_120+6], al
0x18005bd1a  mov     byte ptr [rbp+170h+var_120+7], r13b
0x18005bd1e  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18005bd25  lea     rcx, [rsp+270h+var_210]
0x18005bd2a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bd2f  lea     rdx, [rbp+170h+var_120]
0x18005bd33  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005bd38  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005bd3d  mov     r8, qword ptr [rbp+170h+var_110]
0x18005bd41  mov     rcx, rax
0x18005bd44  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bd49  lea     rdx, aSelectNull; " SELECT NULL"
0x18005bd50  mov     rcx, rax
0x18005bd53  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bd58  lea     r9, [r15+1C0h]
0x18005bd5f  mov     edx, 802h
0x18005bd64  lea     rax, [rsp+270h+var_220]
0x18005bd69  mov     [rsp+270h+Reserved], rax
0x18005bd6e  lea     r8, [rbp+170h+var_E0]
0x18005bd75  call    ?BuildText@?$RowType@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18005bd7a  lea     rdx, aFrom_0; " FROM "
0x18005bd81  lea     rcx, [rsp+270h+var_210]
0x18005bd86  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bd8b  lea     rdx, [rbp+170h+var_E0]
0x18005bd92  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005bd9a  cmova   rdx, [rbp+170h+var_E0]
0x18005bda2  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005bda9  mov     rcx, rax
0x18005bdac  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bdb1  lea     edx, [r13+10h]
0x18005bdb5  lea     rax, [rsp+270h+var_220]
0x18005bdba  mov     [rsp+270h+Reserved], rax
0x18005bdbf  lea     r9, [rbp+170h+var_120]
0x18005bdc3  lea     r8, [rbp+170h+var_E0]
0x18005bdca  call    ?BuildText@?$RowType@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18005bdcf  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18005bdd6  lea     rcx, [rsp+270h+var_210]
0x18005bddb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bde0  lea     rdx, [rbp+170h+var_120]
0x18005bde4  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005bde9  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005bdee  mov     r8, qword ptr [rbp+170h+var_110]
0x18005bdf2  mov     rcx, rax
0x18005bdf5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bdfa  lea     rdx, aOn; " ON ("
0x18005be01  mov     rcx, rax
0x18005be04  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005be09  mov     r12d, r13d
0x18005be0c  mov     rax, [r15+1E8h]
0x18005be13  mov     [rsp+270h+var_240], rax
0x18005be18  mov     rsi, [r15+1E0h]
0x18005be1f  lea     r13d, [r12+40h]
0x18005be24  cmp     rsi, rax
0x18005be27  jz      loc_18005BEC7
0x18005be2d  lea     rbx, [rsi+38h]
0x18005be31  test    r12, r12
0x18005be34  jz      short loc_18005BE47
0x18005be36  lea     rdx, aAnd_1; " AND "
0x18005be3d  lea     rcx, [rsp+270h+var_210]
0x18005be42  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005be47  lea     rdx, [rbp+170h+var_120]
0x18005be4b  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005be50  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005be55  mov     r8, qword ptr [rbp+170h+var_110]
0x18005be59  lea     rcx, [rsp+270h+var_210]
0x18005be5e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005be63  lea     rdx, asc_1801D0CE8; "."
0x18005be6a  mov     rcx, rax
0x18005be6d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005be72  mov     rdx, rsi
0x18005be75  cmp     qword ptr [rbx-20h], 0Fh
0x18005be7a  jbe     short loc_18005BE7F
0x18005be7c  mov     rdx, [rsi]
0x18005be7f  mov     r8, [rbx-28h]
0x18005be83  mov     rcx, rax
0x18005be86  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005be8b  lea     rdx, asc_1801D5B8C; " = "
0x18005be92  mov     rcx, rax
0x18005be95  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005be9a  lea     rdx, [rbx-18h]
0x18005be9e  cmp     qword ptr [rbx], 0Fh
0x18005bea2  jbe     short loc_18005BEA7
0x18005bea4  mov     rdx, [rdx]
0x18005bea7  mov     r8, [rbx-8]
0x18005beab  mov     rcx, rax
0x18005beae  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005beb3  inc     r12
0x18005beb6  add     rsi, r13
0x18005beb9  add     rbx, r13
0x18005bebc  cmp     rsi, [rsp+270h+var_240]
0x18005bec1  jnz     loc_18005BE31
0x18005bec7  lea     rdx, aWhere; ") WHERE "
0x18005bece  lea     rcx, [rsp+270h+var_210]
0x18005bed3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bed8  lea     rdx, [rbp+170h+var_120]
0x18005bedc  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005bee1  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005bee6  mov     r8, qword ptr [rbp+170h+var_110]
0x18005beea  mov     rcx, rax
0x18005beed  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bef2  lea     r12, asc_1801D0CE8; "."
0x18005bef9  mov     rdx, r12
0x18005befc  mov     rcx, rax
0x18005beff  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bf04  mov     rcx, rax
0x18005bf07  xorps   xmm0, xmm0
0x18005bf0a  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18005bf11  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18005bf19  movdqu  [rbp+170h+var_B0], xmm1
0x18005bf21  movsd   xmm0, qword ptr cs:aDigestId; "digest_id"
0x18005bf29  movsd   [rbp+170h+Block], xmm0
0x18005bf31  mov     al, byte ptr cs:aDigestId+8; "d"
0x18005bf37  mov     byte ptr [rbp+170h+Block+8], al
0x18005bf3d  xor     esi, esi
0x18005bf3f  mov     byte ptr [rbp+170h+Block+9], sil
0x18005bf46  lea     r8d, [rsi+9]
0x18005bf4a  lea     rdx, [rbp+170h+Block]
0x18005bf51  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bf56  lea     rdx, aIsNull; " IS NULL;"
0x18005bf5d  mov     rcx, rax
0x18005bf60  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bf65  nop
0x18005bf66  mov     ebx, 1000h
0x18005bf6b  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18005bf72  cmp     rax, 0Fh
0x18005bf76  jbe     short loc_18005BFB7
0x18005bf78  mov     rcx, [rbp+170h+Block]; Block
0x18005bf7f  mov     rdx, rcx
0x18005bf82  inc     rax
0x18005bf85  cmp     rax, rbx
0x18005bf88  jb      short loc_18005BFB1
0x18005bf8a  mov     rcx, [rcx-8]
0x18005bf8e  sub     rdx, rcx
0x18005bf91  lea     rax, [rdx-8]
0x18005bf95  cmp     rax, 1Fh
0x18005bf99  jbe     short loc_18005BFB1
0x18005bf9b  mov     [rsp+270h+Reserved], rsi; Reserved
0x18005bfa0  xor     r9d, r9d; LineNo
0x18005bfa3  xor     r8d, r8d; FileName
0x18005bfa6  xor     edx, edx; FunctionName
0x18005bfa8  xor     ecx, ecx; Expression
0x18005bfaa  call    cs:__imp__invoke_watson
0x18005bfb1  call    cs:__imp_free
0x18005bfb7  lea     rcx, [rbp+170h+var_80]
0x18005bfbe  call    ?MapName@?$Table@VDigests@Tables@Meta@RepoMan@@V?$TablePolicy@UDigests@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UDigest_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDigests@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UDigest@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Digests,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Digests,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Digest_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Digests,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Digest,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x18005bfc3  nop
0x18005bfc4  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18005bfcb  lea     rcx, [rsp+270h+var_210]
0x18005bfd0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005bfd5  lea     rdx, [rbp+170h+var_80]
0x18005bfdc  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18005bfe4  cmova   rdx, [rbp+170h+var_80]
0x18005bfec  mov     r8, qword ptr [rbp+170h+var_70]
0x18005bff3  mov     rcx, rax
0x18005bff6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005bffb  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x18005c002  mov     rcx, rax
0x18005c005  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c00a  lea     rdx, aInsertInto; "INSERT INTO "
0x18005c011  lea     rcx, [rsp+270h+var_210]
0x18005c016  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c01b  lea     rdx, [rbp+170h+var_80]
0x18005c022  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18005c02a  cmova   rdx, [rbp+170h+var_80]
0x18005c032  mov     r8, qword ptr [rbp+170h+var_70]
0x18005c039  mov     rcx, rax
0x18005c03c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c041  lea     rdx, aSelect; " SELECT "
0x18005c048  mov     rcx, rax
0x18005c04b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c050  lea     rdx, [rbp+170h+var_E0]
0x18005c057  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005c05f  cmova   rdx, [rbp+170h+var_E0]
0x18005c067  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005c06e  mov     rcx, rax
0x18005c071  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c076  mov     rdx, r12
0x18005c079  mov     rcx, rax
0x18005c07c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c081  mov     rcx, rax
0x18005c084  xorps   xmm0, xmm0
0x18005c087  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18005c08b  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18005c093  movdqu  [rbp+170h+var_F0], xmm1
0x18005c09b  movsd   xmm0, qword ptr cs:aDigestId; "digest_id"
0x18005c0a3  movsd   [rbp+170h+var_100], xmm0
0x18005c0a8  mov     al, byte ptr cs:aDigestId+8; "d"
0x18005c0ae  mov     byte ptr [rbp+170h+var_100+8], al
0x18005c0b1  mov     byte ptr [rbp+170h+var_100+9], sil
0x18005c0b5  mov     r8d, 9
0x18005c0bb  lea     rdx, [rbp+170h+var_100]
0x18005c0bf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c0c4  lea     rdx, aAsIncoming; " AS incoming, "
0x18005c0cb  mov     rcx, rax
0x18005c0ce  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c0d3  lea     rdx, [rbp+170h+var_120]
0x18005c0d7  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005c0dc  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005c0e1  mov     r8, qword ptr [rbp+170h+var_110]
0x18005c0e5  mov     rcx, rax
0x18005c0e8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c0ed  mov     rdx, r12
0x18005c0f0  mov     rcx, rax
0x18005c0f3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c0f8  mov     rcx, rax
0x18005c0fb  xorps   xmm0, xmm0
0x18005c0fe  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18005c105  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18005c10d  movdqu  [rbp+170h+var_B0], xmm1
0x18005c115  movsd   xmm0, qword ptr cs:aDigestId; "digest_id"
0x18005c11d  movsd   [rbp+170h+Block], xmm0
0x18005c125  mov     al, byte ptr cs:aDigestId+8; "d"
0x18005c12b  mov     byte ptr [rbp+170h+Block+8], al
0x18005c131  mov     byte ptr [rbp+170h+Block+9], sil
0x18005c138  mov     r8d, 9
0x18005c13e  lea     rdx, [rbp+170h+Block]
0x18005c145  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c14a  lea     rdx, aAsClientFrom; " AS client FROM "
0x18005c151  mov     rcx, rax
0x18005c154  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c159  lea     rdx, [rbp+170h+var_E0]
0x18005c160  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18005c168  cmova   rdx, [rbp+170h+var_E0]
0x18005c170  mov     r8, qword ptr [rbp+170h+var_D0]
0x18005c177  mov     rcx, rax
0x18005c17a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c17f  lea     rdx, aInnerJoin; " INNER JOIN "
0x18005c186  mov     rcx, rax
0x18005c189  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c18e  lea     rdx, [rbp+170h+var_120]
0x18005c192  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18005c197  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005c19c  mov     r8, qword ptr [rbp+170h+var_110]
0x18005c1a0  mov     rcx, rax
0x18005c1a3  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005c1a8  lea     rdx, aOn; " ON ("
0x18005c1af  mov     rcx, rax
0x18005c1b2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005c1b7  nop
0x18005c1b8  lea     rcx, [rbp+170h+Block]
0x18005c1bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005c1c4  mov     r12d, 4DE1h
0x18005c1ca  mov     [rbp+170h+Block], r12
0x18005c1d1  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18005c1d9  movdqu  [rbp+170h+var_B0], xmm6
0x18005c1e1  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x18005c1e8  cmp     rax, 0Fh
0x18005c1ec  jbe     short loc_18005C22A
0x18005c1ee  mov     rcx, [rbp+170h+var_100]; Block
0x18005c1f2  mov     rdx, rcx
0x18005c1f5  inc     rax
0x18005c1f8  cmp     rax, rbx
0x18005c1fb  jb      short loc_18005C224
0x18005c1fd  mov     rcx, [rcx-8]
0x18005c201  sub     rdx, rcx
0x18005c204  lea     rax, [rdx-8]
  ... truncated ...
```
