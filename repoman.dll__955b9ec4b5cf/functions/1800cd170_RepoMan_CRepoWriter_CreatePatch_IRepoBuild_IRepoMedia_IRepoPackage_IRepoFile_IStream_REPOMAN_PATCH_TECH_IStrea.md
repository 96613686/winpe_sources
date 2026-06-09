# RepoMan::CRepoWriter::CreatePatch(IRepoBuild *,IRepoMedia *,IRepoPackage *,IRepoFile *,IStream *,_REPOMAN_PATCH_TECH,IStream *)

- ea: `0x1800cd170`
- end: `0x1800ce19c`
- name: `?CreatePatch@CRepoWriter@RepoMan@@UEAAJPEAUIRepoBuild@@PEAUIRepoMedia@@PEAUIRepoPackage@@PEAUIRepoFile@@PEAUIStream@@W4_REPOMAN_PATCH_TECH@@4@Z`
- size: `4140`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008574`
- `0x180009638`
- `0x180013518`
- `0x1800136dc`
- `0x180016b9c`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002e5bc`
- `0x18002e6b8`
- `0x18002f940`
- `0x18002f9b0`
- `0x18002fa20`
- `0x18002fdf0`
- `0x1800cd170`
- `0x18018aed8`
- `0x18018b53c`
- `0x18018b9e4`
- `0x1801927e4`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`
- `0x1801a02e0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd555`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd5a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd605`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd667`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd6c9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdb4c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdbb0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdc00`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd555`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd5a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd605`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd667`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cd6c9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdb4c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdbb0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cdc00`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd54e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd59c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd5fe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd660`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd6c2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdb45`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdba9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdbf9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd54e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd59c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd5fe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd660`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cd6c2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdb45`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdba9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cdbf9`

## string_xrefs

- `0x1800cd20f`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cd6f3`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cdf3f`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800ce005`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cd1d9`: `CRepoWriter.CreatePatch`
- `0x1800cd9e9`: `Unable to create patch `

## pseudocode

```c
// Hidden C++ exception states: #wind=31 #try_helpers=1
__int64 __fastcall RepoMan::CRepoWriter::CreatePatch(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct IStream *a6,
        int a7,
        RepoMan *a8)
{
  RepoMan *v9; // rcx
  const char *v10; // r9
  RepoMan *v11; // rcx
  const char *v12; // r9
  RepoMan *v13; // rcx
  const char *v14; // r9
  __int64 v15; // r14
  __int64 v16; // rax
  __m128i si128; // xmm7
  _BYTE *v18; // rax
  unsigned __int64 v19; // r15
  size_t v20; // r8
  _BYTE *v21; // rax
  size_t v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  void *v26; // rcx
  __int64 v27; // rax
  __m128i v28; // xmm6
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  RepoMan *v34; // rcx
  const char *v35; // r9
  _BYTE *v36; // rax
  void **v37; // rcx
  unsigned __int64 v38; // r14
  size_t v39; // r8
  CHAR *v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rdx
  unsigned int v45; // eax
  const char *v46; // r9
  unsigned int v47; // eax
  const char *v48; // r9
  struct IStream *v49; // r9
  CHAR *v50; // rdx
  __int64 v51; // rcx
  struct IStream *v52; // rcx
  void *v53; // rcx
  unsigned __int64 v54; // xmm0_8
  void *v55; // rcx
  unsigned __int64 v56; // xmm7_8
  void *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned int v61; // eax
  const char *v62; // r9
  unsigned __int64 v63; // rax
  CHAR *v64; // rdx
  __int64 v65; // rcx
  struct IStream *v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v71; // r15
  unsigned int (__fastcall *v72)(__int64, __int64, const WCHAR *, _QWORD, __int64, _QWORD *, __int64 *); // rsi
  _QWORD *v73; // rax
  RepoMan *v74; // rcx
  const char *v75; // r9
  WCHAR *v76; // rsi
  __int64 v77; // r15
  unsigned int (__fastcall *v78)(__int64, __int64, WCHAR *, struct IStream *, WCHAR *, __int64, int, __int64 *); // r14
  __int64 v79; // rcx
  RepoMan *v80; // rcx
  const char *v81; // r9
  __int64 v82; // rcx
  __int64 v83; // rcx
  struct IStream *v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // [rsp+50h] [rbp-358h] BYREF
  __int64 v89; // [rsp+58h] [rbp-350h] BYREF
  __int64 v90; // [rsp+60h] [rbp-348h] BYREF
  struct IStream *v91; // [rsp+68h] [rbp-340h] BYREF
  __int64 v92; // [rsp+70h] [rbp-338h] BYREF
  __int64 v93; // [rsp+78h] [rbp-330h] BYREF
  __int64 v94; // [rsp+80h] [rbp-328h] BYREF
  unsigned __int64 v95; // [rsp+88h] [rbp-320h] BYREF
  __int64 v96; // [rsp+90h] [rbp-318h]
  __int64 v97; // [rsp+98h] [rbp-310h]
  __int64 v98; // [rsp+A0h] [rbp-308h]
  __int64 v99; // [rsp+A8h] [rbp-300h]
  _BYTE v100[16]; // [rsp+B0h] [rbp-2F8h] BYREF
  char v101[8]; // [rsp+C0h] [rbp-2E8h] BYREF
  _BYTE v102[128]; // [rsp+C8h] [rbp-2E0h] BYREF
  _QWORD v103[13]; // [rsp+148h] [rbp-260h] BYREF
  CHAR MultiByteStr[16]; // [rsp+1B0h] [rbp-1F8h] BYREF
  __m128i v105; // [rsp+1C0h] [rbp-1E8h]
  void *Buf1[2]; // [rsp+1D0h] [rbp-1D8h] BYREF
  size_t v107; // [rsp+1E0h] [rbp-1C8h]
  unsigned __int64 v108; // [rsp+1E8h] [rbp-1C0h]
  void *Block[2]; // [rsp+1F0h] [rbp-1B8h] BYREF
  __m128i v110; // [rsp+200h] [rbp-1A8h]
  void *v111[2]; // [rsp+210h] [rbp-198h] BYREF
  __m128i v112; // [rsp+220h] [rbp-188h]
  void *v113[2]; // [rsp+230h] [rbp-178h] BYREF
  __m128i v114; // [rsp+240h] [rbp-168h]
  void *Src[2]; // [rsp+250h] [rbp-158h] BYREF
  __m128i v116; // [rsp+260h] [rbp-148h]
  WCHAR v117[8]; // [rsp+270h] [rbp-138h] BYREF
  __m128i v118; // [rsp+280h] [rbp-128h]
  void *v119[2]; // [rsp+290h] [rbp-118h] BYREF
  __m128i v120; // [rsp+2A0h] [rbp-108h]
  void *v121[2]; // [rsp+2B0h] [rbp-F8h] BYREF
  __m128i v122; // [rsp+2C0h] [rbp-E8h]
  void *v123[2]; // [rsp+2D0h] [rbp-D8h] BYREF
  __int128 v124; // [rsp+2E0h] [rbp-C8h]
  WCHAR WideCharStr[8]; // [rsp+2F0h] [rbp-B8h] BYREF
  __m128i v126; // [rsp+300h] [rbp-A8h]
  _BYTE v127[40]; // [rsp+310h] [rbp-98h] BYREF
  __int64 v128; // [rsp+338h] [rbp-70h]

  v99 = a4;
  v98 = a3;
  v97 = a2;
  v96 = a1;
  RepoMan::Tracer::Tracer(v127, 1, "CRepoWriter.CreatePatch");
  v90 = 0;
  v9 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v90);
  RepoMan::RaiseExceptionIfFailed(v9, 364, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v10);
  v89 = 0;
  v11 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 56LL))(v90, &v89);
  RepoMan::RaiseExceptionIfFailed(v11, 366, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v12);
  v92 = 0;
  v13 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 56LL))(a5, &v92);
  RepoMan::RaiseExceptionIfFailed(v13, 368, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v14);
  v15 = RepoMan::StreamBase<>::Size(a8);
  v88 = v15;
  v16 = RepoMan::SHA256::ComputeHash(v111, a8);
  RepoMan::Encoding::EncodeBase64(Buf1, v16);
  std::vector<unsigned char>::_Tidy(v111);
  *(_OWORD *)v121 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v122 = si128;
  LOBYTE(v121[0]) = 0;
  *(_OWORD *)v119 = 0;
  v120 = si128;
  LOBYTE(v119[0]) = 0;
  v18 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v89 + 24LL))(v89);
  *(_OWORD *)v123 = 0;
  v124 = 0;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( v18[v20] );
  std::string::_Construct<1,char const *>(v123, v18, v20);
  v21 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 24LL))(v92);
  *(_OWORD *)Src = 0;
  v116 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  std::string::_Construct<1,char const *>(Src, v21, v22);
  v23 = std::string::append(Src);
  *(_OWORD *)v113 = 0;
  v114 = 0;
  *(_OWORD *)v113 = *(_OWORD *)v23;
  v114 = *(__m128i *)(v23 + 16);
  *(_BYTE *)v23 = 0;
  *(_QWORD *)(v23 + 16) = 0;
  *(_QWORD *)(v23 + 24) = 15;
  v24 = std::string::append(v113);
  *(_OWORD *)v111 = 0;
  v112 = 0;
  *(_OWORD *)v111 = *(_OWORD *)v24;
  v112 = *(__m128i *)(v24 + 16);
  *(_BYTE *)v24 = 0;
  *(_QWORD *)(v24 + 16) = 0;
  *(_QWORD *)(v24 + 24) = 15;
  v25 = std::string::append(v111);
  *(_OWORD *)Block = *(_OWORD *)v25;
  v110 = *(__m128i *)(v25 + 16);
  *(_BYTE *)v25 = 0;
  *(_QWORD *)(v25 + 16) = 0;
  *(_QWORD *)(v25 + 24) = 15;
  v26 = (void *)std::operator+<char>(WideCharStr, Block, v123);
  v27 = std::string::append(v26);
  *(_OWORD *)MultiByteStr = 0;
  v105 = 0;
  *(_OWORD *)MultiByteStr = *(_OWORD *)v27;
  v105 = *(__m128i *)(v27 + 16);
  *(_BYTE *)v27 = 0;
  *(_QWORD *)(v27 + 16) = 0;
  *(_QWORD *)(v27 + 24) = 15;
  std::string::_Tidy_deallocate(WideCharStr);
  *(_QWORD *)WideCharStr = 19937;
  v28 = _mm_load_si128((const __m128i *)&_xmm);
  v126 = v28;
  if ( v110.m128i_i64[1] > 0xFuLL )
  {
    v29 = Block[0];
    if ( (unsigned __int64)(v110.m128i_i64[1] + 1) >= 0x1000 )
    {
      v29 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v29 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v29);
  }
  if ( v112.m128i_i64[1] > 0xFuLL )
  {
    v30 = v111[0];
    if ( (unsigned __int64)(v112.m128i_i64[1] + 1) >= 0x1000 )
    {
      v30 = (void *)*((_QWORD *)v111[0] - 1);
      if ( (unsigned __int64)((char *)v111[0] - (char *)v30 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v30);
  }
  v111[0] = (void *)19937;
  v112 = v28;
  if ( v114.m128i_i64[1] > 0xFuLL )
  {
    v31 = v113[0];
    if ( (unsigned __int64)(v114.m128i_i64[1] + 1) >= 0x1000 )
    {
      v31 = (void *)*((_QWORD *)v113[0] - 1);
      if ( (unsigned __int64)((char *)v113[0] - (char *)v31 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v31);
  }
  v113[0] = (void *)19937;
  v114 = v28;
  if ( v116.m128i_i64[1] > 0xFuLL )
  {
    v32 = Src[0];
    if ( (unsigned __int64)(v116.m128i_i64[1] + 1) >= 0x1000 )
    {
      v32 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v32 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v32);
  }
  Src[0] = (void *)19937;
  v116 = v28;
  if ( *((_QWORD *)&v124 + 1) > 0xFu )
  {
    v33 = v123[0];
    if ( (unsigned __int64)(*((_QWORD *)&v124 + 1) + 1LL) >= 0x1000 )
    {
      v33 = (void *)*((_QWORD *)v123[0] - 1);
      if ( (unsigned __int64)((char *)v123[0] - (char *)v33 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v33);
  }
  v95 = 0;
  v34 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v90 + 48LL))(v90, &v95);
  RepoMan::RaiseExceptionIfFailed(v34, 375, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v35);
  if ( v15 == v95 )
  {
    v36 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v89 + 24LL))(v89);
    do
      ++v19;
    while ( v36[v19] );
    v37 = Buf1;
    if ( v108 > 0xF )
      v37 = (void **)Buf1[0];
    v38 = v107;
    v39 = v107;
    if ( v19 < v107 )
      v39 = v19;
    if ( !memcmp(v37, v36, v39) && v38 >= v19 && v38 <= v19 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v100);
      std::operator<<<std::char_traits<char>>(
        (__int64)v101,
        (__int64)"Base file and target file are identical, skipping ");
      v40 = MultiByteStr;
      if ( v105.m128i_i64[1] > 0xFuLL )
        v40 = *(CHAR **)MultiByteStr;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v101, (__int64)v40, v105.m128i_u64[0]);
      std::stringbuf::str(v102, Block);
      RepoMan::Logger::CreateValue((unsigned int)&v88, 1, 8, (unsigned int)Block, 0);
      std::string::_Tidy_deallocate(Block);
      Block[0] = (void *)19937;
      v110 = v28;
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v103);
      v103[0] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)v103);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 48LL))(v128, &v88);
      v41 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
      }
      std::string::_Tidy_deallocate(MultiByteStr);
      *(_QWORD *)MultiByteStr = 19937;
      v105 = v28;
      std::string::_Tidy_deallocate(v119);
      std::string::_Tidy_deallocate(v121);
      std::string::_Tidy_deallocate(Buf1);
      Buf1[0] = (void *)19937;
      v107 = 0;
      v108 = 31;
      v42 = v92;
      if ( v92 )
      {
        v92 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v90;
      if ( v90 )
      {
        v90 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
LABEL_94:
      RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v127);
      return 1;
    }
    v15 = v88;
  }
  v45 = (*(__int64 (__fastcall **)(RepoMan *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a8 + 40LL))(a8, 0, 0, 0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v45, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v46);
  v47 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a6->lpVtbl->Seek)(a6, 0, 0, 0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v47, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v48);
  RepoMan::ComPtr<IStream>::Make<RepoMan::MemoryStream,>(&v91);
  if ( !RepoMan::CreateDeltaFile(a8, v91, a6, v49) )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v100);
    std::operator<<<std::char_traits<char>>((__int64)v101, (__int64)"Unable to create patch ");
    v50 = MultiByteStr;
    if ( v105.m128i_i64[1] > 0xFuLL )
      v50 = *(CHAR **)MultiByteStr;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v101, (__int64)v50, v105.m128i_u64[0]);
    std::stringbuf::str(v102, Block);
    RepoMan::Logger::CreateValue((unsigned int)&v88, 1, 8, (unsigned int)Block, 0);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v110 = v28;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v103);
    v103[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v103);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 48LL))(v128, &v88);
    v51 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
    }
    v52 = v91;
    if ( v91 )
    {
      v91 = 0;
      ((void (__fastcall *)(struct IStream *))v52->lpVtbl->Release)(v52);
    }
    if ( v105.m128i_i64[1] > 0xFuLL )
    {
      v53 = *(void **)MultiByteStr;
      if ( (unsigned __int64)(v105.m128i_i64[1] + 1) >= 0x1000 )
      {
        v53 = *(void **)(*(_QWORD *)MultiByteStr - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)MultiByteStr - (_QWORD)v53 - 8LL) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v53);
    }
    *(_QWORD *)MultiByteStr = 19937;
    v105 = v28;
    v54 = _mm_srli_si128(si128, 8).m128i_u64[0];
    if ( v54 > 0xF )
    {
      v55 = v119[0];
      if ( v54 + 1 >= 0x1000 )
      {
        v55 = (void *)*((_QWORD *)v119[0] - 1);
        if ( (unsigned __int64)((char *)v119[0] - (char *)v55 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v55);
    }
    v56 = _mm_srli_si128(si128, 8).m128i_u64[0];
    if ( v56 > 0xF )
    {
      v57 = v121[0];
      if ( v56 + 1 >= 0x1000 )
      {
        v57 = (void *)*((_QWORD *)v121[0] - 1);
        if ( (unsigned __int64)((char *)v121[0] - (char *)v57 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v57);
    }
    std::string::_Tidy_deallocate(Buf1);
    Buf1[0] = (void *)19937;
    v107 = 0;
    v108 = 31;
    v58 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    goto LABEL_94;
  }
  v61 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))v91->lpVtbl->Seek)(v91, 0, 0, 0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v61, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v62);
  v63 = RepoMan::StreamBase<>::Size(v91);
  if ( v63 >= v95 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v100);
    v64 = MultiByteStr;
    if ( v105.m128i_i64[1] > 0xFuLL )
      v64 = *(CHAR **)MultiByteStr;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v101, (__int64)v64, v105.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      (__int64)v101,
      (__int64)" delta file size is >= target file size, skipping.");
    std::stringbuf::str(v102, Block);
    RepoMan::Logger::CreateValue((unsigned int)&v88, 1, 8, (unsigned int)Block, 0);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v110 = v28;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v103);
    v103[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v103);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 48LL))(v128, &v88);
    v65 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
    }
    v66 = v91;
    if ( v91 )
    {
      v91 = 0;
      ((void (__fastcall *)(struct IStream *))v66->lpVtbl->Release)(v66);
    }
    std::string::_Tidy_deallocate(MultiByteStr);
    *(_QWORD *)MultiByteStr = 19937;
    v105 = v28;
    std::string::_Tidy_deallocate(v119);
    std::string::_Tidy_deallocate(v121);
    std::string::_Tidy_deallocate(Buf1);
    Buf1[0] = (void *)19937;
    v107 = 0;
    v108 = 31;
    v67 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v69 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    goto LABEL_94;
  }
  v94 = 0;
  v71 = v96;
  v72 = *(unsigned int (__fastcall **)(__int64, __int64, const WCHAR *, _QWORD, __int64, _QWORD *, __int64 *))(*(_QWORD *)v96 + 96LL);
  v73 = (_QWORD *)RepoMan::utf8_to_wstring(WideCharStr, (LPCCH)Buf1);
  if ( v73[3] > 7u )
    v73 = (_QWORD *)*v73;
  v74 = (RepoMan *)v72(v71, v97, L"SHA256", 0, v15, v73, &v94);
  RepoMan::RaiseExceptionIfFailed(v74, 403, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v75);
  std::wstring::_Tidy_deallocate(WideCharStr);
  v93 = 0;
  RepoMan::utf8_to_wstring(v117, MultiByteStr);
  v76 = v117;
  if ( v118.m128i_i64[1] > 7uLL )
    v76 = *(WCHAR **)v117;
  v77 = v98;
  v78 = *(unsigned int (__fastcall **)(__int64, __int64, WCHAR *, struct IStream *, WCHAR *, __int64, int, __int64 *))(*(_QWORD *)v98 + 40LL);
  v79 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v80 = (RepoMan *)v78(v77, v99, v76, v91, v76, v94, a7, &v93);
  RepoMan::RaiseExceptionIfFailed(v80, 408, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v81);
  std::wstring::_Tidy_deallocate(v117);
  *(_QWORD *)v117 = 19937;
  v118 = _mm_load_si128((const __m128i *)&_xmm);
  v82 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  }
  v83 = v94;
  if ( v94 )
  {
    v94 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  }
  v84 = v91;
  if ( v91 )
  {
    v91 = 0;
    ((void (__fastcall *)(struct IStream *))v84->lpVtbl->Release)(v84);
  }
  std::string::_Tidy_deallocate(MultiByteStr);
  *(_QWORD *)MultiByteStr = 19937;
  v105 = v28;
  std::string::_Tidy_deallocate(v119);
  std::string::_Tidy_deallocate(v121);
  std::string::_Tidy_deallocate(Buf1);
  Buf1[0] = (void *)19937;
  v107 = 0;
  v108 = 31;
  v85 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  }
  v86 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
  }
  v87 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
  }
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v127);
  return 0;
}

```

## disassembly

```asm
0x1800cd170  mov     rax, rsp
0x1800cd173  push    rbx
0x1800cd174  push    rsi
0x1800cd175  push    rdi
0x1800cd176  push    r12
0x1800cd178  push    r13
0x1800cd17a  push    r14
0x1800cd17c  push    r15
0x1800cd17e  sub     rsp, 370h
0x1800cd185  movaps  xmmword ptr [rax-48h], xmm6
0x1800cd189  movaps  xmmword ptr [rax-58h], xmm7
0x1800cd18d  mov     rax, cs:__security_cookie
0x1800cd194  xor     rax, rsp
0x1800cd197  mov     [rsp+3A8h+var_68], rax
0x1800cd19f  mov     [rsp+3A8h+var_300], r9
0x1800cd1a7  mov     [rsp+3A8h+var_308], r8
0x1800cd1af  mov     [rsp+3A8h+var_310], rdx
0x1800cd1b7  mov     [rsp+3A8h+var_318], rcx
0x1800cd1bf  mov     rdi, [rsp+3A8h+arg_20]
0x1800cd1c7  mov     r13, [rsp+3A8h+arg_28]
0x1800cd1cf  mov     r12, [rsp+3A8h+arg_38]
0x1800cd1d7  xor     ebx, ebx
0x1800cd1d9  lea     r8, aCrepowriterCre; "CRepoWriter.CreatePatch"
0x1800cd1e0  lea     esi, [rbx+1]
0x1800cd1e3  mov     edx, esi
0x1800cd1e5  lea     rcx, [rsp+3A8h+var_98]
0x1800cd1ed  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800cd1f2  nop
0x1800cd1f3  mov     [rsp+3A8h+var_348], rbx
0x1800cd1f8  mov     rax, [rdi]
0x1800cd1fb  lea     rdx, [rsp+3A8h+var_348]
0x1800cd200  mov     rcx, rdi
0x1800cd203  mov     rax, [rax+28h]
0x1800cd207  call    cs:__guard_dispatch_icall_fptr
0x1800cd20d  mov     ecx, eax; this
0x1800cd20f  lea     r14, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cd216  mov     r8, r14; int
0x1800cd219  mov     edx, 16Ch; int
0x1800cd21e  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800cd223  mov     [rsp+3A8h+var_350], rbx
0x1800cd228  mov     rcx, [rsp+3A8h+var_348]
0x1800cd22d  mov     rax, [rcx]
0x1800cd230  lea     rdx, [rsp+3A8h+var_350]
0x1800cd235  mov     rax, [rax+38h]
0x1800cd239  call    cs:__guard_dispatch_icall_fptr
0x1800cd23f  mov     ecx, eax; this
0x1800cd241  mov     r8, r14; int
0x1800cd244  mov     edx, 16Eh; int
0x1800cd249  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800cd24e  mov     [rsp+3A8h+var_338], rbx
0x1800cd253  mov     rax, [rdi]
0x1800cd256  lea     rdx, [rsp+3A8h+var_338]
0x1800cd25b  mov     rcx, rdi
0x1800cd25e  mov     rax, [rax+38h]
0x1800cd262  call    cs:__guard_dispatch_icall_fptr
0x1800cd268  mov     ecx, eax; this
0x1800cd26a  mov     r8, r14; int
0x1800cd26d  mov     edx, 170h; int
0x1800cd272  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800cd277  mov     rcx, r12
0x1800cd27a  call    ?Size@?$StreamBase@$$V@RepoMan@@SA_KPEAUIStream@@@Z; RepoMan::StreamBase<>::Size(IStream *)
0x1800cd27f  mov     r14, rax
0x1800cd282  mov     [rsp+3A8h+var_358], rax
0x1800cd287  mov     rdx, r12
0x1800cd28a  lea     rcx, [rsp+3A8h+var_198]
0x1800cd292  call    ?ComputeHash@SHA256@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@@Z; RepoMan::SHA256::ComputeHash(IStream *)
0x1800cd297  mov     rdx, rax
0x1800cd29a  lea     rcx, [rsp+3A8h+Buf1]
0x1800cd2a2  call    ?EncodeBase64@Encoding@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; RepoMan::Encoding::EncodeBase64(std::vector<uchar> const &)
0x1800cd2a7  nop
0x1800cd2a8  lea     rcx, [rsp+3A8h+var_198]
0x1800cd2b0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cd2b5  xorps   xmm0, xmm0
0x1800cd2b8  movups  xmmword ptr [rsp+3A8h+var_F8], xmm0
0x1800cd2c0  movdqa  xmm7, cs:__xmm@000000000000000f0000000000000000
0x1800cd2c8  movdqu  [rsp+3A8h+var_E8], xmm7
0x1800cd2d1  mov     byte ptr [rsp+3A8h+var_F8], bl
0x1800cd2d8  movups  xmmword ptr [rsp+3A8h+var_118], xmm0
0x1800cd2e0  movdqu  [rsp+3A8h+var_108], xmm7
0x1800cd2e9  mov     byte ptr [rsp+3A8h+var_118], bl
0x1800cd2f0  mov     rcx, [rsp+3A8h+var_350]
0x1800cd2f5  mov     rax, [rcx]
0x1800cd2f8  mov     rax, [rax+18h]
0x1800cd2fc  call    cs:__guard_dispatch_icall_fptr
0x1800cd302  xorps   xmm0, xmm0
0x1800cd305  movups  xmmword ptr [rsp+3A8h+var_D8], xmm0
0x1800cd30d  xorps   xmm1, xmm1
0x1800cd310  movdqu  [rsp+3A8h+var_C8], xmm1
0x1800cd319  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800cd31d  mov     r8, r15
0x1800cd320  inc     r8
0x1800cd323  cmp     [rax+r8], bl
0x1800cd327  jnz     short loc_1800CD320
0x1800cd329  mov     rdx, rax
0x1800cd32c  lea     rcx, [rsp+3A8h+var_D8]
0x1800cd334  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800cd339  nop
0x1800cd33a  mov     rcx, [rsp+3A8h+var_338]
0x1800cd33f  mov     rax, [rcx]
0x1800cd342  mov     rax, [rax+18h]
0x1800cd346  call    cs:__guard_dispatch_icall_fptr
0x1800cd34c  xorps   xmm0, xmm0
0x1800cd34f  movups  xmmword ptr [rsp+3A8h+Src], xmm0
0x1800cd357  xorps   xmm1, xmm1
0x1800cd35a  movdqu  [rsp+3A8h+var_148], xmm1
0x1800cd363  mov     r8, r15
0x1800cd366  inc     r8
0x1800cd369  cmp     [rax+r8], bl
0x1800cd36d  jnz     short loc_1800CD366
0x1800cd36f  mov     rdx, rax
0x1800cd372  lea     rcx, [rsp+3A8h+Src]
0x1800cd37a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800cd37f  nop
0x1800cd380  mov     r8, rsi
0x1800cd383  lea     rdx, asc_1801D0CE8; "."
0x1800cd38a  lea     rcx, [rsp+3A8h+Src]; Src
0x1800cd392  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800cd397  xorps   xmm0, xmm0
0x1800cd39a  movups  xmmword ptr [rsp+3A8h+var_178], xmm0
0x1800cd3a2  xorps   xmm1, xmm1
0x1800cd3a5  movdqu  [rsp+3A8h+var_168], xmm1
0x1800cd3ae  movups  xmm0, xmmword ptr [rax]
0x1800cd3b1  movups  xmmword ptr [rsp+3A8h+var_178], xmm0
0x1800cd3b9  movups  xmm1, xmmword ptr [rax+10h]
0x1800cd3bd  movups  [rsp+3A8h+var_168], xmm1
0x1800cd3c5  mov     [rax], bl
0x1800cd3c7  mov     [rax+10h], rbx
0x1800cd3cb  mov     edi, 0Fh
0x1800cd3d0  mov     [rax+18h], rdi
0x1800cd3d4  lea     rdx, [rsp+3A8h+Buf1]
0x1800cd3dc  cmp     [rsp+3A8h+var_1C0], rdi
0x1800cd3e4  cmova   rdx, [rsp+3A8h+Buf1]
0x1800cd3ed  mov     r8, [rsp+3A8h+var_1C8]
0x1800cd3f5  lea     rcx, [rsp+3A8h+var_178]; Src
0x1800cd3fd  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800cd402  xorps   xmm0, xmm0
0x1800cd405  movups  xmmword ptr [rsp+3A8h+var_198], xmm0
0x1800cd40d  xorps   xmm1, xmm1
0x1800cd410  movdqu  [rsp+3A8h+var_188], xmm1
0x1800cd419  movups  xmm0, xmmword ptr [rax]
0x1800cd41c  movups  xmmword ptr [rsp+3A8h+var_198], xmm0
0x1800cd424  movups  xmm1, xmmword ptr [rax+10h]
0x1800cd428  movups  [rsp+3A8h+var_188], xmm1
0x1800cd430  mov     [rax], bl
0x1800cd432  mov     [rax+10h], rbx
0x1800cd436  mov     [rax+18h], rdi
0x1800cd43a  mov     r8, rsi
0x1800cd43d  lea     rdx, asc_1801D0CE8; "."
0x1800cd444  lea     rcx, [rsp+3A8h+var_198]; Src
0x1800cd44c  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800cd451  movups  xmm0, xmmword ptr [rax]
0x1800cd454  movups  xmmword ptr [rsp+3A8h+Block], xmm0
0x1800cd45c  movups  xmm1, xmmword ptr [rax+10h]
0x1800cd460  movups  [rsp+3A8h+var_1A8], xmm1
0x1800cd468  mov     [rax], bl
0x1800cd46a  mov     [rax+10h], rbx
0x1800cd46e  mov     [rax+18h], rdi
0x1800cd472  lea     r8, [rsp+3A8h+var_D8]
0x1800cd47a  lea     rdx, [rsp+3A8h+Block]
0x1800cd482  lea     rcx, [rsp+3A8h+WideCharStr]
0x1800cd48a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800cd48f  nop
0x1800cd490  lea     r8d, [rdi-9]
0x1800cd494  lea     rdx, aDelta_0; ".delta"
0x1800cd49b  mov     rcx, rax; Src
0x1800cd49e  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1800cd4a3  xorps   xmm0, xmm0
0x1800cd4a6  movups  xmmword ptr [rsp+3A8h+MultiByteStr], xmm0
0x1800cd4ae  xorps   xmm1, xmm1
0x1800cd4b1  movdqu  [rsp+3A8h+var_1E8], xmm1
0x1800cd4ba  movups  xmm0, xmmword ptr [rax]
0x1800cd4bd  movups  xmmword ptr [rsp+3A8h+MultiByteStr], xmm0
0x1800cd4c5  movups  xmm1, xmmword ptr [rax+10h]
0x1800cd4c9  movups  [rsp+3A8h+var_1E8], xmm1
0x1800cd4d1  mov     [rax], bl
0x1800cd4d3  mov     [rax+10h], rbx
0x1800cd4d7  mov     [rax+18h], rdi
0x1800cd4db  lea     rcx, [rsp+3A8h+WideCharStr]
0x1800cd4e3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cd4e8  mov     qword ptr [rsp+3A8h+WideCharStr], 4DE1h
0x1800cd4f4  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800cd4fc  movdqu  [rsp+3A8h+var_A8], xmm6
0x1800cd505  mov     rax, qword ptr [rsp+3A8h+var_1A8+8]
0x1800cd50d  mov     esi, 1000h
0x1800cd512  cmp     rax, rdi
0x1800cd515  mov     edi, 1Fh
0x1800cd51a  jbe     short loc_1800CD55C
0x1800cd51c  mov     rcx, [rsp+3A8h+Block]; Block
0x1800cd524  mov     rdx, rcx
0x1800cd527  inc     rax
0x1800cd52a  cmp     rax, rsi
0x1800cd52d  jb      short loc_1800CD555
0x1800cd52f  mov     rcx, [rcx-8]
0x1800cd533  sub     rdx, rcx
0x1800cd536  lea     rax, [rdx-8]
0x1800cd53a  cmp     rax, rdi
0x1800cd53d  jbe     short loc_1800CD555
0x1800cd53f  mov     [rsp+3A8h+Reserved], rbx; Reserved
0x1800cd544  xor     r9d, r9d; LineNo
0x1800cd547  xor     r8d, r8d; FileName
0x1800cd54a  xor     edx, edx; FunctionName
0x1800cd54c  xor     ecx, ecx; Expression
0x1800cd54e  call    cs:__imp__invoke_watson
0x1800cd555  call    cs:__imp_free
0x1800cd55b  nop
0x1800cd55c  mov     rax, qword ptr [rsp+3A8h+var_188+8]
0x1800cd564  cmp     rax, 0Fh
0x1800cd568  jbe     short loc_1800CD5A9
0x1800cd56a  mov     rcx, [rsp+3A8h+var_198]; Block
0x1800cd572  mov     rdx, rcx
0x1800cd575  inc     rax
0x1800cd578  cmp     rax, rsi
0x1800cd57b  jb      short loc_1800CD5A3
0x1800cd57d  mov     rcx, [rcx-8]
0x1800cd581  sub     rdx, rcx
0x1800cd584  lea     rax, [rdx-8]
0x1800cd588  cmp     rax, rdi
0x1800cd58b  jbe     short loc_1800CD5A3
0x1800cd58d  mov     [rsp+3A8h+Reserved], rbx; Reserved
0x1800cd592  xor     r9d, r9d; LineNo
0x1800cd595  xor     r8d, r8d; FileName
0x1800cd598  xor     edx, edx; FunctionName
0x1800cd59a  xor     ecx, ecx; Expression
0x1800cd59c  call    cs:__imp__invoke_watson
0x1800cd5a3  call    cs:__imp_free
0x1800cd5a9  mov     [rsp+3A8h+var_198], 4DE1h
0x1800cd5b5  movdqu  [rsp+3A8h+var_188], xmm6
0x1800cd5be  mov     rax, qword ptr [rsp+3A8h+var_168+8]
0x1800cd5c6  cmp     rax, 0Fh
0x1800cd5ca  jbe     short loc_1800CD60B
0x1800cd5cc  mov     rcx, [rsp+3A8h+var_178]; Block
0x1800cd5d4  mov     rdx, rcx
0x1800cd5d7  inc     rax
0x1800cd5da  cmp     rax, rsi
0x1800cd5dd  jb      short loc_1800CD605
0x1800cd5df  mov     rcx, [rcx-8]
0x1800cd5e3  sub     rdx, rcx
0x1800cd5e6  lea     rax, [rdx-8]
0x1800cd5ea  cmp     rax, rdi
0x1800cd5ed  jbe     short loc_1800CD605
0x1800cd5ef  mov     [rsp+3A8h+Reserved], rbx; Reserved
0x1800cd5f4  xor     r9d, r9d; LineNo
0x1800cd5f7  xor     r8d, r8d; FileName
0x1800cd5fa  xor     edx, edx; FunctionName
0x1800cd5fc  xor     ecx, ecx; Expression
0x1800cd5fe  call    cs:__imp__invoke_watson
0x1800cd605  call    cs:__imp_free
0x1800cd60b  mov     [rsp+3A8h+var_178], 4DE1h
0x1800cd617  movdqu  [rsp+3A8h+var_168], xmm6
0x1800cd620  mov     rax, qword ptr [rsp+3A8h+var_148+8]
0x1800cd628  cmp     rax, 0Fh
0x1800cd62c  jbe     short loc_1800CD66D
0x1800cd62e  mov     rcx, [rsp+3A8h+Src]; Block
0x1800cd636  mov     rdx, rcx
0x1800cd639  inc     rax
0x1800cd63c  cmp     rax, rsi
0x1800cd63f  jb      short loc_1800CD667
0x1800cd641  mov     rcx, [rcx-8]
0x1800cd645  sub     rdx, rcx
0x1800cd648  lea     rax, [rdx-8]
0x1800cd64c  cmp     rax, rdi
0x1800cd64f  jbe     short loc_1800CD667
0x1800cd651  mov     [rsp+3A8h+Reserved], rbx; Reserved
0x1800cd656  xor     r9d, r9d; LineNo
0x1800cd659  xor     r8d, r8d; FileName
0x1800cd65c  xor     edx, edx; FunctionName
0x1800cd65e  xor     ecx, ecx; Expression
0x1800cd660  call    cs:__imp__invoke_watson
0x1800cd667  call    cs:__imp_free
0x1800cd66d  mov     [rsp+3A8h+Src], 4DE1h
0x1800cd679  movdqu  [rsp+3A8h+var_148], xmm6
0x1800cd682  mov     rax, qword ptr [rsp+3A8h+var_C8+8]
0x1800cd68a  cmp     rax, 0Fh
0x1800cd68e  jbe     short loc_1800CD6CF
0x1800cd690  mov     rcx, [rsp+3A8h+var_D8]; Block
0x1800cd698  mov     rdx, rcx
0x1800cd69b  inc     rax
0x1800cd69e  cmp     rax, rsi
0x1800cd6a1  jb      short loc_1800CD6C9
0x1800cd6a3  mov     rcx, [rcx-8]
0x1800cd6a7  sub     rdx, rcx
0x1800cd6aa  lea     rax, [rdx-8]
0x1800cd6ae  cmp     rax, rdi
0x1800cd6b1  jbe     short loc_1800CD6C9
0x1800cd6b3  mov     [rsp+3A8h+Reserved], rbx; Reserved
0x1800cd6b8  xor     r9d, r9d; LineNo
0x1800cd6bb  xor     r8d, r8d; FileName
0x1800cd6be  xor     edx, edx; FunctionName
0x1800cd6c0  xor     ecx, ecx; Expression
0x1800cd6c2  call    cs:__imp__invoke_watson
0x1800cd6c9  call    cs:__imp_free
0x1800cd6cf  mov     [rsp+3A8h+var_320], rbx
0x1800cd6d7  mov     rcx, [rsp+3A8h+var_348]
0x1800cd6dc  mov     rax, [rcx]
0x1800cd6df  lea     rdx, [rsp+3A8h+var_320]
0x1800cd6e7  mov     rax, [rax+30h]
0x1800cd6eb  call    cs:__guard_dispatch_icall_fptr
0x1800cd6f1  mov     ecx, eax; this
0x1800cd6f3  lea     r8, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cd6fa  mov     edx, 177h; int
  ... truncated ...
```
