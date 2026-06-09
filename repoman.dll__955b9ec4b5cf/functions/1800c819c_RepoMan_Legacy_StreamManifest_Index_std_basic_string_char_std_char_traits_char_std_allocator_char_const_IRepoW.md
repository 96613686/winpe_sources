# RepoMan::Legacy::StreamManifest::Index(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,IRepoWriter *,IRepoBuild *,IRepoCulture *,_REPOMAN_FILE_TAGS)

- ea: `0x1800c819c`
- end: `0x1800c8fe0`
- name: `?Index@StreamManifest@Legacy@RepoMan@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUIRepoWriter@@PEAUIRepoBuild@@PEAUIRepoCulture@@W4_REPOMAN_FILE_TAGS@@@Z`
- size: `3652`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800cefb0`

## callees

- `0x18000145c`
- `0x180001504`
- `0x180001ffc`
- `0x180008574`
- `0x1800244bc`
- `0x18002d958`
- `0x18002f940`
- `0x18002f9b0`
- `0x18003386c`
- `0x1800385d8`
- `0x1800c5348`
- `0x1800c5460`
- `0x1800c7a68`
- `0x1800c7e38`
- `0x1800c819c`
- `0x1800d17a8`
- `0x1800d1840`
- `0x1800d18f0`
- `0x1800d25f0`
- `0x1800d4a04`
- `0x1800d4bdc`
- `0x1800d51fc`
- `0x1800dc7b4`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b53c`
- `0x18018b9e4`
- `0x18019a840`
- `0x18019a984`
- `0x18019f7a0`
- `0x18019f800`
- `0x1801a0240`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c83e0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c85f5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c867f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c8817`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c8941`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c83e0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c85f5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c867f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c8817`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c8941`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c8a9d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c8af0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c8a9d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c8af0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8ecc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8ee2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8ecc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8ee2`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800c887c`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800c887c`

## string_xrefs

- `0x1800c8332`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c847a`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c8b44`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c8cdb`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c8d54`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c8d8e`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c84f3`: `c2r32.dll`
- `0x1800c854d`: `appvisvstream32.dll`
- `0x1800c8520`: `c2r64.dll`
- `0x1800c85a7`: `appvisvsubsystems32.dll`
- `0x1800c857a`: `appvisvstream64.dll`
- `0x1800c8a32`: `root\mcxml`
- `0x1800c85d4`: `appvisvsubsystems64.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
__int64 __fastcall RepoMan::Legacy::StreamManifest::Index(
        __int64 *a1,
        const CHAR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 v6; // r15
  __int64 *v9; // rdi
  _BYTE *v10; // rax
  __int64 v11; // r14
  size_t v12; // r8
  __int128 *v13; // rbx
  char *v14; // rdi
  size_t v15; // r8
  __int128 *i; // rcx
  char *v17; // rax
  WCHAR *v18; // rcx
  unsigned int v19; // eax
  const char *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rax
  size_t v27; // rcx
  __m128i *v28; // r13
  __m128i si128; // xmm7
  __int64 (__fastcall *v30)(__int64, __int64, __int64, wchar_t *, __int64 *); // rbx
  __int64 v31; // rdx
  __int64 v32; // r8
  wchar_t *v33; // r9
  unsigned int v34; // eax
  const char *v35; // r9
  __int64 *FileData; // rax
  __int64 v37; // rcx
  __int64 *v38; // rdx
  __int64 v39; // rbx
  _QWORD *v40; // rax
  _QWORD *v41; // rbx
  __int64 *v42; // rsi
  __int64 v43; // rax
  __int128 v44; // xmm6
  wchar_t *v45; // r15
  _OWORD *v46; // rdi
  _QWORD *v47; // rdx
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  unsigned __int64 v51; // rbx
  void **v52; // rsi
  unsigned __int64 v53; // rcx
  unsigned __int64 v54; // rdi
  size_t v55; // rcx
  wchar_t *v56; // rax
  wchar_t **v57; // rsi
  wchar_t *v58; // rdx
  wchar_t **v59; // rax
  wchar_t **v60; // r15
  wchar_t **v61; // rdi
  signed __int64 v62; // rsi
  wchar_t **v63; // rsi
  unsigned __int64 v64; // rdi
  size_t v65; // rcx
  void *v66; // rax
  wchar_t *v67; // rdi
  wchar_t *v68; // rbx
  wchar_t **v69; // rax
  wchar_t *j; // rax
  wchar_t *k; // rcx
  wchar_t **v72; // rdi
  unsigned __int64 v73; // rax
  char *v74; // rsi
  const wchar_t *m; // rcx
  wchar_t *v76; // rax
  int v77; // edx
  wchar_t *v78; // rbx
  __int64 v79; // rbx
  wchar_t *v80; // rcx
  void *v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // r15
  unsigned int v84; // eax
  const char *v85; // r9
  void **v86; // r8
  void **v87; // r9
  unsigned int v88; // eax
  const char *v89; // r9
  unsigned int v90; // eax
  const char *v91; // r9
  __int64 *StreamUnits; // rax
  __int64 v93; // rcx
  __int64 v94; // rsi
  __int64 v95; // rbx
  __int64 v96; // rbx
  const CHAR *v97; // rax
  unsigned int v98; // eax
  const char *v99; // r9
  unsigned int v100; // eax
  const char *v101; // r9
  unsigned int v102; // eax
  const char *v103; // r9
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  __int64 result; // rax
  __int64 v110; // rcx
  __int64 v111; // [rsp+70h] [rbp-98h] BYREF
  __int64 v112; // [rsp+78h] [rbp-90h] BYREF
  wchar_t *v113; // [rsp+80h] [rbp-88h] BYREF
  __int64 v114; // [rsp+88h] [rbp-80h]
  __int64 v115; // [rsp+90h] [rbp-78h]
  __int64 v116; // [rsp+98h] [rbp-70h] BYREF
  __int64 v117; // [rsp+A0h] [rbp-68h]
  __int64 v118; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v119; // [rsp+B0h] [rbp-58h]
  __int64 v120; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v121; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v122; // [rsp+D0h] [rbp-38h]
  __m128i *v123; // [rsp+D8h] [rbp-30h]
  __int64 *v124; // [rsp+E0h] [rbp-28h]
  __int64 v125; // [rsp+E8h] [rbp-20h]
  __int64 v126; // [rsp+F0h] [rbp-18h]
  __int64 v127; // [rsp+F8h] [rbp-10h]
  wchar_t **v128; // [rsp+100h] [rbp-8h]
  _OWORD *v129; // [rsp+108h] [rbp+0h]
  _QWORD v130[2]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v131; // [rsp+120h] [rbp+18h]
  _QWORD v132[3]; // [rsp+128h] [rbp+20h] BYREF
  wchar_t *S[2]; // [rsp+140h] [rbp+38h] BYREF
  __m128i v134; // [rsp+150h] [rbp+48h]
  wchar_t v135[8]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v136; // [rsp+170h] [rbp+68h]
  void *Src[2]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 v138; // [rsp+198h] [rbp+90h]
  unsigned __int64 v139; // [rsp+1A0h] [rbp+98h]
  __int128 v140; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int64 v141; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v142; // [rsp+1C0h] [rbp+B8h]
  _OWORD v143[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  WCHAR WideCharStr[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  __m128i v145; // [rsp+1F8h] [rbp+F0h]
  _OWORD v146[2]; // [rsp+208h] [rbp+100h] BYREF
  _OWORD v147[2]; // [rsp+228h] [rbp+120h] BYREF
  _OWORD v148[2]; // [rsp+248h] [rbp+140h] BYREF
  _OWORD v149[2]; // [rsp+268h] [rbp+160h] BYREF
  _OWORD v150[2]; // [rsp+288h] [rbp+180h] BYREF
  _OWORD v151[2]; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v152; // [rsp+2C8h] [rbp+1C0h] BYREF

  v6 = a4;
  v126 = a4;
  v9 = a1;
  v119 = a1;
  v127 = a5;
  v120 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 32LL))(a5, &v120);
  v10 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v120 + 24LL))(v120);
  v140 = 0;
  v141 = 0;
  v142 = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  std::string::_Construct<1,char const *>(&v140, v10, v12);
  v13 = &v140;
  if ( v142 > 0xF )
    v13 = (__int128 *)v140;
  if ( v141 >= 2 )
  {
    v14 = (char *)v13 + v141;
    v15 = v141 - 1;
    for ( i = v13; ; i = (__int128 *)(v17 + 1) )
    {
      v17 = (char *)memchr(i, 49, v15);
      if ( !v17 )
      {
        v11 = -1;
        goto LABEL_11;
      }
      if ( *(_WORD *)v17 == 13617 )
        break;
      v15 = v14 - 1 - (v17 + 1);
    }
    v11 = v17 - (char *)v13;
LABEL_11:
    v9 = v119;
  }
  v111 = 0;
  RepoMan::utf8_to_wstring(WideCharStr, a2);
  v18 = WideCharStr;
  if ( v145.m128i_i64[1] > 7uLL )
    v18 = *(WCHAR **)WideCharStr;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, WCHAR *, __int64 *))(*(_QWORD *)a3 + 40LL))(
          a3,
          v6,
          0,
          1,
          v18,
          &v111);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v19, 477, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v20);
  v121 = 0;
  v122 = 0;
  v23 = 0x4EC4EC4EC4EC4EC5LL * ((v9[1] - *v9) >> 3);
  if ( v23 )
  {
    if ( v23 > 0x276276276276276LL )
      std::vector<RepoMan::ComPtr<IRepoPatch>>::_Xlength(0x276276276276276LL, v21, v22);
    v24 = 8 * ((v9[1] - *v9) >> 3);
    if ( v24 )
    {
      v27 = 8 * ((v9[1] - *v9) >> 3);
      if ( v24 < 0x1000 )
      {
        v25 = (__int64)malloc(v27);
        if ( !v25 )
          std::_Xbad_alloc();
      }
      else
      {
        v25 = std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v27);
      }
    }
    else
    {
      v25 = 0;
    }
    v121.m128i_i64[0] = v25;
    v121.m128i_i64[1] = v25;
    v122 = v25 + v24;
    v123 = &v121;
    v26 = std::_Uninitialized_copy<RepoMan::Legacy::PackageFileData *,RepoMan::Legacy::PackageFileData *,std::allocator<RepoMan::Legacy::PackageFileData>>(
            *v9,
            v9[1],
            v25);
    v123 = (__m128i *)v26;
    v121.m128i_i64[1] = v26;
  }
  else
  {
    v26 = v121.m128i_i64[1];
    v123 = (__m128i *)v121.m128i_i64[1];
  }
  v28 = (__m128i *)v121.m128i_i64[0];
  v125 = v121.m128i_i64[0];
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v121.m128i_i64[0] == v26 )
    goto LABEL_138;
  while ( 2 )
  {
    v118 = 0;
    v30 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3 + 80LL);
    v31 = v28[3].m128i_i64[0];
    *(_OWORD *)v135 = 0;
    v136 = 0;
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)(v31 + 2 * v32) );
    std::wstring::_Construct<1,wchar_t const *>(v135, v31, v32);
    v33 = v135;
    if ( *((_QWORD *)&v136 + 1) > 7u )
      v33 = *(wchar_t **)v135;
    v34 = v30(a3, v6, v127, v33, &v118);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v34, 482, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v35);
    std::wstring::_Tidy_deallocate(v135);
    FileData = (__int64 *)RepoMan::Legacy::StreamManifest::GetFileData(v9, v135, v28);
    v37 = FileData[2];
    FileData[2] = 0;
    v124 = (__int64 *)FileData[1];
    v38 = v124;
    FileData[1] = 0;
    v117 = *FileData;
    v39 = v117;
    *FileData = 0;
    v132[0] = v39;
    v132[1] = v38;
    v132[2] = v37;
    std::vector<RepoMan::Legacy::FileData>::~vector<RepoMan::Legacy::FileData>(v135);
    memset(v146, 0, sizeof(v146));
    std::wstring::_Construct<1,wchar_t const *>(v146, L"c2r32.dll", 9);
    memset(v147, 0, sizeof(v147));
    std::wstring::_Construct<1,wchar_t const *>(v147, L"c2r64.dll", 9);
    memset(v148, 0, sizeof(v148));
    std::wstring::_Construct<1,wchar_t const *>(v148, L"appvisvstream32.dll", 19);
    memset(v149, 0, sizeof(v149));
    std::wstring::_Construct<1,wchar_t const *>(v149, L"appvisvstream64.dll", 19);
    memset(v150, 0, sizeof(v150));
    std::wstring::_Construct<1,wchar_t const *>(v150, L"appvisvsubsystems32.dll", 23);
    memset(v151, 0, sizeof(v151));
    std::wstring::_Construct<1,wchar_t const *>(v151, L"appvisvsubsystems64.dll", 23);
    v113 = 0;
    v114 = 0;
    v40 = malloc(0x40u);
    v41 = v40;
    if ( !v40 )
      std::_Xbad_alloc();
    *v40 = v40;
    v40[1] = v40;
    v40[2] = v40;
    *((_WORD *)v40 + 12) = 257;
    v113 = (wchar_t *)v40;
    v42 = (__int64 *)v146;
    do
    {
      v43 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(
              &v113,
              v143,
              v41,
              v42);
      v44 = *(_OWORD *)v43;
      v131 = *(_QWORD *)(v43 + 16);
      if ( !(_BYTE)v131 )
      {
        if ( v114 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v45 = v113;
        v128 = &v113;
        v129 = 0;
        v46 = malloc(0x40u);
        if ( !v46 )
          std::_Xbad_alloc();
        v129 = v46;
        *(_QWORD *)&v143[0] = v46 + 2;
        v46[2] = 0;
        *((_QWORD *)v46 + 6) = 0;
        *((_QWORD *)v46 + 7) = 0;
        v47 = v42;
        if ( (unsigned __int64)v42[3] > 7 )
          v47 = (_QWORD *)*v42;
        std::wstring::_Construct<2,wchar_t const *>(v46 + 2, v47, v42[2]);
        *(_QWORD *)v46 = v45;
        *((_QWORD *)v46 + 1) = v45;
        *((_QWORD *)v46 + 2) = v45;
        *((_WORD *)v46 + 12) = 0;
        v129 = 0;
        v143[0] = v44;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(
          &v113,
          v143,
          v46);
      }
      v42 += 4;
    }
    while ( v42 != &v152 );
    `eh vector destructor iterator'(v146, 0x20u, 6u, std::wstring::~wstring);
    v48 = (__int64 *)v117;
    while ( v48 != v124 )
    {
      v49 = *v48;
      *(_OWORD *)Src = 0;
      v138 = 0;
      v139 = 0;
      v50 = -1;
      do
        ++v50;
      while ( *(_WORD *)(v49 + 2 * v50) );
      std::wstring::_Construct<1,wchar_t const *>(Src, v49, v50);
      *(_OWORD *)S = 0;
      v134 = 0;
      v51 = v138;
      v52 = Src;
      if ( v139 > 7 )
        v52 = (void **)Src[0];
      if ( v138 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v138 > 7 )
      {
        v54 = v138 | 7;
        if ( (v138 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          if ( v54 < 0xA )
            v54 = 10;
        }
        else
        {
          v54 = 0x7FFFFFFFFFFFFFFELL;
        }
        if ( v54 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v55 = 2 * (v54 + 1);
        if ( v55 )
        {
          if ( v55 < 0x1000 )
          {
            v56 = (wchar_t *)malloc(v55);
            if ( !v56 )
              std::_Xbad_alloc();
          }
          else
          {
            v56 = (wchar_t *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v55);
          }
        }
        else
        {
          v56 = 0;
        }
        S[0] = v56;
        v134.m128i_i64[0] = v51;
        v134.m128i_i64[1] = v54;
        memmove(v56, v52, 2 * v51 + 2);
        v53 = v134.m128i_u64[1];
        v51 = v134.m128i_i64[0];
      }
      else
      {
        v134.m128i_i64[0] = v138;
        v53 = 7;
        v134.m128i_i64[1] = 7;
        *(_OWORD *)S = *(_OWORD *)v52;
      }
      v57 = S;
      v58 = S[0];
      if ( v53 > 7 )
        v57 = (wchar_t **)S[0];
      v59 = S;
      if ( v53 > 7 )
        v59 = (wchar_t **)S[0];
      v60 = (wchar_t **)((char *)v59 + 2 * v51);
      v61 = S;
      if ( v53 > 7 )
        v61 = (wchar_t **)S[0];
      if ( v61 != v60 )
      {
        v62 = (char *)v57 - (char *)v61;
        do
        {
          *(_WORD *)((char *)v61 + v62) = tolower(*(unsigned __int16 *)v61);
          v61 = (wchar_t **)((char *)v61 + 2);
        }
        while ( v61 != v60 );
        v53 = v134.m128i_u64[1];
        v51 = v134.m128i_i64[0];
        v58 = S[0];
      }
      *(_QWORD *)&v143[0] = v135;
      *(_OWORD *)v135 = 0;
      v136 = 0u;
      v63 = S;
      if ( v53 > 7 )
        v63 = (wchar_t **)v58;
      if ( v51 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v51 > 7 )
      {
        v64 = v51 | 7;
        if ( (v51 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          if ( v64 < 0xA )
            v64 = 10;
        }
        else
        {
          v64 = 0x7FFFFFFFFFFFFFFELL;
        }
        if ( v64 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v65 = 2 * (v64 + 1);
        if ( v65 )
        {
          if ( v65 < 0x1000 )
          {
            v66 = malloc(v65);
            if ( !v66 )
              std::_Xbad_alloc();
          }
          else
          {
            v66 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v65);
          }
        }
        else
        {
          v66 = 0;
        }
        *(_QWORD *)v135 = v66;
        *(_QWORD *)&v136 = v51;
        *((_QWORD *)&v136 + 1) = v64;
        memmove(v66, v63, 2 * v51 + 2);
      }
      else
      {
        *(_QWORD *)&v136 = v51;
        *((_QWORD *)&v136 + 1) = 7;
        *(_OWORD *)v135 = *(_OWORD *)v63;
      }
      v67 = v113;
      v68 = *(wchar_t **)v113;
      while ( v68 != v67 && std::wstring::find(v135, v68 + 16) == -1 )
      {
        v69 = (wchar_t **)*((_QWORD *)v68 + 2);
        if ( *((_BYTE *)v69 + 25) )
        {
          for ( j = (wchar_t *)*((_QWORD *)v68 + 1);
                !*((_BYTE *)j + 25) && v68 == *((wchar_t **)j + 2);
                j = (wchar_t *)*((_QWORD *)j + 1) )
          {
            v68 = j;
          }
          v68 = j;
        }
        else
        {
          v68 = (wchar_t *)*((_QWORD *)v68 + 2);
          for ( k = *v69; !*((_BYTE *)k + 25); k = *(wchar_t **)k )
            v68 = k;
        }
      }
      std::wstring::_Tidy_deallocate(v135);
      if ( v68 != v113 )
      {
        v72 = S;
        v73 = v134.m128i_u64[1];
        if ( v134.m128i_i64[1] > 7uLL )
          v72 = (wchar_t **)S[0];
        if ( v134.m128i_i64[0] >= 0xAuLL )
        {
          v74 = (char *)v72 + 2 * v134.m128i_i64[0] - 18;
          for ( m = (const wchar_t *)v72; ; m = v78 + 1 )
          {
            v76 = wmemchr(m, 0x72u, (v74 - (char *)m) >> 1);
            v78 = v76;
            if ( !v76 )
              break;
            if ( !wmemcmp(v76, L"root\\mcxml", (unsigned int)(v77 - 104)) )
            {
              v79 = ((char *)v78 - (char *)v72) >> 1;
              v73 = v134.m128i_u64[1];
              goto LABEL_106;
            }
          }
          v73 = v134.m128i_u64[1];
LABEL_107:
          if ( v73 > 7 )
          {
            v80 = S[0];
            if ( 2 * v73 + 2 >= 0x1000 )
            {
              v80 = (wchar_t *)*((_QWORD *)S[0] - 1);
              if ( (unsigned __int64)((char *)S[0] - (char *)v80 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v80);
          }
          S[0] = (wchar_t *)19937;
          v134 = si128;
          if ( v139 > 7 )
          {
            v81 = Src[0];
            if ( 2 * v139 + 2 >= 0x1000 )
            {
              v81 = (void *)*((_QWORD *)Src[0] - 1);
              if ( (unsigned __int64)((char *)Src[0] - (char *)v81 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v81);
          }
          goto LABEL_130;
        }
        v79 = -1;
LABEL_106:
        if ( v79 == -1 )
          goto LABEL_107;
      }
      v116 = 0;
      v82 = v117;
      v83 = v126;
      v84 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)a3 + 96LL))(
              a3,
              v126,
              L"PseudoHash",
              0,
              *(unsigned int *)(v117 + 80),
              L"pseudoDigest",
              &v116);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v84, 528, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v85);
      v112 = 0;
      v86 = Src;
      if ( v139 > 7 )
        v86 = (void **)Src[0];
      v87 = Src;
      if ( v139 > 7 )
        v87 = (void **)Src[0];
      v88 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void **, __int64, void **, _QWORD, _DWORD, int, bool, __int64 *))(*(_QWORD *)a3 + 232LL))(
              a3,
              v83,
              v111,
              v87,
              v116,
              v86,
              0,
              0,
              a6,
              v11 != -1,
              &v112);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v88, 540, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v89);
      v90 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a3 + 128LL))(a3, v83, v118, v112);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v90, 544, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v91);
      StreamUnits = (__int64 *)RepoMan::Legacy::StreamManifest::GetStreamUnits(v119, v135, v82);
      v93 = StreamUnits[2];
      StreamUnits[2] = 0;
      v94 = StreamUnits[1];
      StreamUnits[1] = 0;
      v95 = *StreamUnits;
      *StreamUnits = 0;
      v130[0] = v95;
      v130[1] = v94;
      v131 = v93;
      std::vector<RepoMan::Legacy::StreamUnit>::~vector<RepoMan::Legacy::StreamUnit>(v135);
      if ( v95 != v94 )
      {
        v96 = v95 + 40;
        do
        {
          v97 = (const CHAR *)RepoMan::Encoding::EncodeBase64(v143, v96 - 32);
          RepoMan::utf8_to_wstring(v135, v97);
          std::string::_Tidy_deallocate(v143);
          v115 = 0;
          v98 = (*(__int64 (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)a3 + 96LL))(a3, v83, L"SHA256");
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v98, 552, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v99);
          v100 = (*(__int64 (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)a3 + 96LL))(a3, v83, L"SHA256");
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v100, 554, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v101);
          v102 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64))(*(_QWORD *)a3 + 112LL))(
                   a3,
                   v83,
                   v112,
                   0,
                   v115);
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v102, 555, (int)"src\\repoman\\src\\inc\\StreamManifest.hpp", v103);
          v104 = v115;
          if ( v115 )
          {
            v115 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
          }
          std::wstring::_Tidy_deallocate(v135);
          v96 += 96;
        }
        while ( v96 - 40 != v94 );
        v28 = (__m128i *)v125;
      }
      std::vector<RepoMan::Legacy::StreamUnit>::~vector<RepoMan::Legacy::StreamUnit>(v130);
      v105 = v112;
      if ( v112 )
      {
        v112 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      }
      v106 = v116;
      if ( v116 )
      {
        v116 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
      }
      std::wstring::_Tidy_deallocate(S);
      S[0] = (wchar_t *)19937;
      v134 = si128;
      std::wstring::_Tidy_deallocate(Src);
LABEL_130:
      v48 = (__int64 *)(v117 + 104);
      v117 += 104;
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v113);
    std::vector<RepoMan::Legacy::FileData>::~vector<RepoMan::Legacy::FileData>(v132);
    v107 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
    }
    v28 = (__m128i *)((char *)v28 + 104);
    v125 = (__int64)v28;
    if ( v28 != v123 )
    {
      v9 = v119;
      v6 = v126;
      continue;
    }
    break;
  }
LABEL_138:
  std::vector<RepoMan::Legacy::PackageFileData>::_Tidy(&v121);
  v121 = _mm_load_si128((const __m128i *)&_xmm);
  v122 = 19937;
  std::wstring::_Tidy_deallocate(WideCharStr);
  *(_QWORD *)WideCharStr = 19937;
  v145 = si128;
  v108 = v111;
  if ( v111 )
  {
    v111 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
  }
  result = std::string::_Tidy_deallocate(&v140);
  v110 = v120;
  if ( v120 )
  {
    v120 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  }
  return result;
}

```

## disassembly

```asm
0x1800c819c  mov     rax, rsp
0x1800c819f  push    rbp
0x1800c81a0  push    rbx
0x1800c81a1  push    rsi
0x1800c81a2  push    rdi
0x1800c81a3  push    r12
0x1800c81a5  push    r13
0x1800c81a7  push    r14
0x1800c81a9  push    r15
0x1800c81ab  lea     rbp, [rax-238h]
0x1800c81b2  sub     rsp, 2F8h
0x1800c81b9  movaps  xmmword ptr [rax-58h], xmm6
0x1800c81bd  movaps  xmmword ptr [rax-68h], xmm7
0x1800c81c1  mov     rax, cs:__security_cookie
0x1800c81c8  xor     rax, rsp
0x1800c81cb  mov     [rbp+230h+var_70], rax
0x1800c81d2  mov     r15, r9
0x1800c81d5  mov     [rbp+230h+var_248], r9
0x1800c81d9  mov     r12, r8
0x1800c81dc  mov     rsi, rdx
0x1800c81df  mov     rdi, rcx
0x1800c81e2  mov     [rbp+230h+var_288], rcx
0x1800c81e6  mov     rcx, [rbp+230h+arg_20]
0x1800c81ed  mov     [rbp+230h+var_240], rcx
0x1800c81f1  xor     r13d, r13d
0x1800c81f4  mov     [rbp+230h+var_280], r13
0x1800c81f8  mov     rax, [rcx]
0x1800c81fb  lea     rdx, [rbp+230h+var_280]
0x1800c81ff  mov     rax, [rax+20h]
0x1800c8203  call    cs:__guard_dispatch_icall_fptr
0x1800c8209  mov     rcx, [rbp+230h+var_280]
0x1800c820d  mov     rax, [rcx]
0x1800c8210  mov     rax, [rax+18h]
0x1800c8214  call    cs:__guard_dispatch_icall_fptr
0x1800c821a  xorps   xmm0, xmm0
0x1800c821d  movups  [rbp+230h+var_190], xmm0
0x1800c8224  mov     [rbp+230h+var_180], r13
0x1800c822b  mov     [rbp+230h+var_178], r13
0x1800c8232  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800c8236  mov     r8, r14
0x1800c8239  inc     r8
0x1800c823c  cmp     [rax+r8], r13b
0x1800c8240  jnz     short loc_1800C8239
0x1800c8242  mov     rdx, rax
0x1800c8245  lea     rcx, [rbp+230h+var_190]
0x1800c824c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800c8251  nop
0x1800c8252  lea     rbx, [rbp+230h+var_190]
0x1800c8259  cmp     [rbp+230h+var_178], 0Fh
0x1800c8261  cmova   rbx, qword ptr [rbp+230h+var_190]
0x1800c8269  mov     rax, [rbp+230h+var_180]
0x1800c8270  cmp     rax, 2
0x1800c8274  jb      short loc_1800C82B9
0x1800c8276  lea     rdi, [rax+rbx]
0x1800c827a  lea     r8, [rdi-1]
0x1800c827e  sub     r8, rbx
0x1800c8281  mov     rcx, rbx
0x1800c8284  jmp     short loc_1800C829F
0x1800c8286  cmp     word ptr [r14], 3531h
0x1800c828c  jz      loc_1800C83C2
0x1800c8292  inc     r14
0x1800c8295  lea     r8, [rdi-1]
0x1800c8299  sub     r8, r14; MaxCount
0x1800c829c  mov     rcx, r14; Buf
0x1800c829f  mov     edx, 31h ; '1'; Val
0x1800c82a4  call    memchr
0x1800c82a9  test    rax, rax
0x1800c82ac  mov     r14, rax
0x1800c82af  jnz     short loc_1800C8286
0x1800c82b1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800c82b5  mov     rdi, [rbp+230h+var_288]
0x1800c82b9  mov     [rsp+330h+var_2C8], r13
0x1800c82be  mov     rdx, rsi; lpMultiByteStr
0x1800c82c1  lea     rcx, [rbp+230h+WideCharStr]; lpWideCharStr
0x1800c82c8  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x1800c82cd  nop
0x1800c82ce  mov     rax, [r12]
0x1800c82d2  mov     rbx, [rax+28h]
0x1800c82d6  mov     rcx, [rsp+330h+var_2C8]
0x1800c82db  test    rcx, rcx
0x1800c82de  jz      short loc_1800C82F2
0x1800c82e0  mov     [rsp+330h+var_2C8], r13
0x1800c82e5  mov     rax, [rcx]
0x1800c82e8  mov     rax, [rax+10h]
0x1800c82ec  call    cs:__guard_dispatch_icall_fptr
0x1800c82f2  lea     rcx, [rbp+230h+WideCharStr]
0x1800c82f9  cmp     [rbp+230h+var_138], 7
0x1800c8301  cmova   rcx, qword ptr [rbp+230h+WideCharStr]
0x1800c8309  lea     rax, [rsp+330h+var_2C8]
0x1800c830e  mov     [rsp+330h+var_308], rax
0x1800c8313  mov     [rsp+330h+Reserved], rcx
0x1800c8318  mov     r9d, 1
0x1800c831e  xor     r8d, r8d
0x1800c8321  mov     rdx, r15
0x1800c8324  mov     rcx, r12
0x1800c8327  mov     rax, rbx
0x1800c832a  call    cs:__guard_dispatch_icall_fptr
0x1800c8330  mov     ecx, eax; this
0x1800c8332  lea     r8, aSrcRepomanSrcI_8; "src\\repoman\\src\\inc\\StreamManifest."...
0x1800c8339  mov     edx, 1DDh; int
0x1800c833e  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c8343  xorps   xmm0, xmm0
0x1800c8346  movdqu  [rbp+230h+var_278], xmm0
0x1800c834b  mov     [rbp+230h+var_268], r13
0x1800c834f  mov     rax, [rdi+8]
0x1800c8353  sub     rax, [rdi]
0x1800c8356  sar     rax, 3
0x1800c835a  mov     rcx, 4EC4EC4EC4EC4EC5h
0x1800c8364  imul    rax, rcx
0x1800c8368  test    rax, rax
0x1800c836b  jz      loc_1800C83F4
0x1800c8371  mov     rcx, 276276276276276h
0x1800c837b  cmp     rax, rcx
0x1800c837e  ja      loc_1800C8FAA
0x1800c8384  imul    rbx, rax, 68h ; 'h'
0x1800c8388  test    rbx, rbx
0x1800c838b  jnz     short loc_1800C83CA
0x1800c838d  mov     r8, r13
0x1800c8390  mov     qword ptr [rbp+230h+var_278], r8
0x1800c8394  mov     qword ptr [rbp+230h+var_278+8], r8
0x1800c8398  lea     rax, [r8+rbx]
0x1800c839c  mov     [rbp+230h+var_268], rax
0x1800c83a0  lea     rax, [rbp+230h+var_278]
0x1800c83a4  mov     [rbp+230h+var_260], rax
0x1800c83a8  lea     r9, [rbp+230h+var_278]
0x1800c83ac  mov     rdx, [rdi+8]
0x1800c83b0  mov     rcx, [rdi]
0x1800c83b3  call    ??$_Uninitialized_copy@PEAVPackageFileData@Legacy@RepoMan@@PEAV123@V?$allocator@VPackageFileData@Legacy@RepoMan@@@std@@@std@@YAPEAVPackageFileData@Legacy@RepoMan@@PEAV123@00AEAV?$allocator@VPackageFileData@Legacy@RepoMan@@@0@@Z; std::_Uninitialized_copy<RepoMan::Legacy::PackageFileData *,RepoMan::Legacy::PackageFileData *,std::allocator<RepoMan::Legacy::PackageFileData>>(RepoMan::Legacy::PackageFileData *,RepoMan::Legacy::PackageFileData *,RepoMan::Legacy::PackageFileData *,std::allocator<RepoMan::Legacy::PackageFileData> &)
0x1800c83b8  mov     [rbp+230h+var_260], rax
0x1800c83bc  mov     qword ptr [rbp+230h+var_278+8], rax
0x1800c83c0  jmp     short loc_1800C83FC
0x1800c83c2  sub     r14, rbx
0x1800c83c5  jmp     loc_1800C82B5
0x1800c83ca  mov     rcx, rbx; Size
0x1800c83cd  cmp     rbx, 1000h
0x1800c83d4  jb      short loc_1800C83E0
0x1800c83d6  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1800c83db  mov     r8, rax
0x1800c83de  jmp     short loc_1800C8390
0x1800c83e0  call    cs:__imp_malloc
0x1800c83e6  mov     r8, rax
0x1800c83e9  test    rax, rax
0x1800c83ec  jz      loc_1800C8FA4
0x1800c83f2  jmp     short loc_1800C8390
0x1800c83f4  mov     rax, qword ptr [rbp+230h+var_278+8]
0x1800c83f8  mov     [rbp+230h+var_260], rax
0x1800c83fc  mov     r13, qword ptr [rbp+230h+var_278]
0x1800c8400  mov     [rbp+230h+var_250], r13
0x1800c8404  movdqa  xmm7, cs:__xmm@000000000000000f0000000000000000
0x1800c840c  cmp     r13, rax
0x1800c840f  jz      loc_1800C8EE9
0x1800c8415  xor     ecx, ecx
0x1800c8417  mov     [rbp+230h+var_290], rcx
0x1800c841b  mov     rax, [r12]
0x1800c841f  mov     rbx, [rax+50h]
0x1800c8423  mov     rdx, [r13+30h]
0x1800c8427  xorps   xmm0, xmm0
0x1800c842a  movups  xmmword ptr [rbp+230h+var_1D8], xmm0
0x1800c842e  xorps   xmm1, xmm1
0x1800c8431  movdqu  [rbp+230h+var_1C8], xmm1
0x1800c8436  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c843a  inc     r8
0x1800c843d  cmp     [rdx+r8*2], cx
0x1800c8442  jnz     short loc_1800C843A
0x1800c8444  lea     rcx, [rbp+230h+var_1D8]
0x1800c8448  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c844d  nop
0x1800c844e  lea     r9, [rbp+230h+var_1D8]
0x1800c8452  cmp     qword ptr [rbp+230h+var_1C8+8], 7
0x1800c8457  cmova   r9, qword ptr [rbp+230h+var_1D8]
0x1800c845c  lea     rax, [rbp+230h+var_290]
0x1800c8460  mov     [rsp+330h+Reserved], rax
0x1800c8465  mov     r8, [rbp+230h+var_240]
0x1800c8469  mov     rdx, r15
0x1800c846c  mov     rcx, r12
0x1800c846f  mov     rax, rbx
0x1800c8472  call    cs:__guard_dispatch_icall_fptr
0x1800c8478  mov     ecx, eax; this
0x1800c847a  lea     r8, aSrcRepomanSrcI_8; "src\\repoman\\src\\inc\\StreamManifest."...
0x1800c8481  mov     edx, 1E2h; int
0x1800c8486  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c848b  nop
0x1800c848c  lea     rcx, [rbp+230h+var_1D8]
0x1800c8490  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c8495  mov     r8, r13
0x1800c8498  lea     rdx, [rbp+230h+var_1D8]
0x1800c849c  mov     rcx, rdi
0x1800c849f  call    ?GetFileData@StreamManifest@Legacy@RepoMan@@QEAA?AU?$FieldNItems@VFileData@Legacy@RepoMan@@@Meta@3@AEAVPackageFileData@23@@Z; RepoMan::Legacy::StreamManifest::GetFileData(RepoMan::Legacy::PackageFileData &)
0x1800c84a4  mov     rcx, [rax+10h]
0x1800c84a8  xor     r15d, r15d
0x1800c84ab  mov     [rax+10h], r15
0x1800c84af  mov     rdx, [rax+8]
0x1800c84b3  mov     [rbp+230h+var_258], rdx
0x1800c84b7  mov     [rax+8], r15
0x1800c84bb  mov     rbx, [rax]
0x1800c84be  mov     [rbp+230h+var_298], rbx
0x1800c84c2  mov     [rax], r15
0x1800c84c5  mov     [rbp+230h+var_210], rbx
0x1800c84c9  mov     [rbp+230h+var_208], rdx
0x1800c84cd  mov     [rbp+230h+var_200], rcx
0x1800c84d1  lea     rcx, [rbp+230h+var_1D8]
0x1800c84d5  call    ??1?$vector@VFileData@Legacy@RepoMan@@V?$allocator@VFileData@Legacy@RepoMan@@@std@@@std@@QEAA@XZ; std::vector<RepoMan::Legacy::FileData>::~vector<RepoMan::Legacy::FileData>(void)
0x1800c84da  xorps   xmm0, xmm0
0x1800c84dd  movups  [rbp+230h+var_130], xmm0
0x1800c84e4  xorps   xmm1, xmm1
0x1800c84e7  movdqa  [rbp+230h+var_120], xmm1
0x1800c84ef  lea     r8d, [r15+9]
0x1800c84f3  lea     rdx, aC2r32Dll; "c2r32.dll"
0x1800c84fa  lea     rcx, [rbp+230h+var_130]
0x1800c8501  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c8506  nop
0x1800c8507  xorps   xmm0, xmm0
0x1800c850a  movups  [rbp+230h+var_110], xmm0
0x1800c8511  xorps   xmm1, xmm1
0x1800c8514  movdqa  [rbp+230h+var_100], xmm1
0x1800c851c  lea     r8d, [r15+9]
0x1800c8520  lea     rdx, aC2r64Dll; "c2r64.dll"
0x1800c8527  lea     rcx, [rbp+230h+var_110]
0x1800c852e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c8533  nop
0x1800c8534  xorps   xmm0, xmm0
0x1800c8537  movups  [rbp+230h+var_F0], xmm0
0x1800c853e  xorps   xmm1, xmm1
0x1800c8541  movdqa  [rbp+230h+var_E0], xmm1
0x1800c8549  lea     r8d, [r15+13h]
0x1800c854d  lea     rdx, aAppvisvstream3; "appvisvstream32.dll"
0x1800c8554  lea     rcx, [rbp+230h+var_F0]
0x1800c855b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c8560  nop
0x1800c8561  xorps   xmm0, xmm0
0x1800c8564  movups  [rbp+230h+var_D0], xmm0
0x1800c856b  xorps   xmm1, xmm1
0x1800c856e  movdqa  [rbp+230h+var_C0], xmm1
0x1800c8576  lea     r8d, [r15+13h]
0x1800c857a  lea     rdx, aAppvisvstream6; "appvisvstream64.dll"
0x1800c8581  lea     rcx, [rbp+230h+var_D0]
0x1800c8588  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c858d  nop
0x1800c858e  xorps   xmm0, xmm0
0x1800c8591  movups  [rbp+230h+var_B0], xmm0
0x1800c8598  xorps   xmm1, xmm1
0x1800c859b  movdqa  [rbp+230h+var_A0], xmm1
0x1800c85a3  lea     r8d, [r15+17h]
0x1800c85a7  lea     rdx, aAppvisvsubsyst; "appvisvsubsystems32.dll"
0x1800c85ae  lea     rcx, [rbp+230h+var_B0]
0x1800c85b5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c85ba  nop
0x1800c85bb  xorps   xmm0, xmm0
0x1800c85be  movups  [rbp+230h+var_90], xmm0
0x1800c85c5  xorps   xmm1, xmm1
0x1800c85c8  movdqa  [rbp+230h+var_80], xmm1
0x1800c85d0  lea     r8d, [r15+17h]
0x1800c85d4  lea     rdx, aAppvisvsubsyst_0; "appvisvsubsystems64.dll"
0x1800c85db  lea     rcx, [rbp+230h+var_90]
0x1800c85e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c85e7  nop
0x1800c85e8  mov     [rsp+330h+var_2B8], r15
0x1800c85ed  mov     [rbp+230h+var_2B0], r15
0x1800c85f1  lea     ecx, [r15+40h]; Size
0x1800c85f5  call    cs:__imp_malloc
0x1800c85fb  mov     rbx, rax
0x1800c85fe  test    rax, rax
0x1800c8601  jz      loc_1800C8F9E
0x1800c8607  mov     [rax], rax
0x1800c860a  mov     [rax+8], rax
0x1800c860e  mov     [rax+10h], rax
0x1800c8612  mov     word ptr [rax+18h], 101h
0x1800c8618  mov     [rsp+330h+var_2B8], rax
0x1800c861d  lea     rsi, [rbp+230h+var_130]
0x1800c8624  mov     r9, rsi
0x1800c8627  mov     r8, rbx
0x1800c862a  lea     rdx, [rbp+230h+var_170]
0x1800c8631  lea     rcx, [rsp+330h+var_2B8]
0x1800c8636  call    ??$_Find_hint@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_hint<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x1800c863b  movups  xmm6, xmmword ptr [rax]
0x1800c863e  movsd   xmm0, qword ptr [rax+10h]
0x1800c8643  movsd   [rbp+230h+var_218], xmm0
0x1800c8648  cmp     byte ptr [rbp+230h+var_218], r15b
0x1800c864c  jnz     loc_1800C86FA
0x1800c8652  mov     rax, 3FFFFFFFFFFFFFFh
0x1800c865c  cmp     [rbp+230h+var_2B0], rax
0x1800c8660  jz      loc_1800C8FB6
0x1800c8666  mov     r15, [rsp+330h+var_2B8]
0x1800c866b  lea     rax, [rsp+330h+var_2B8]
0x1800c8670  mov     [rbp+230h+var_238], rax
0x1800c8674  xor     ecx, ecx
0x1800c8676  mov     [rbp+230h+var_230], rcx
0x1800c867a  mov     ecx, 40h ; '@'; Size
0x1800c867f  call    cs:__imp_malloc
0x1800c8685  mov     rdi, rax
0x1800c8688  xor     eax, eax
0x1800c868a  test    rdi, rdi
0x1800c868d  jz      loc_1800C8FB0
0x1800c8693  mov     [rbp+230h+var_230], rdi
0x1800c8697  lea     rcx, [rdi+20h]
0x1800c869b  mov     qword ptr [rbp+230h+var_170], rcx
0x1800c86a2  xorps   xmm0, xmm0
0x1800c86a5  movups  xmmword ptr [rcx], xmm0
0x1800c86a8  mov     [rcx+10h], rax
0x1800c86ac  mov     [rcx+18h], rax
  ... truncated ...
```
