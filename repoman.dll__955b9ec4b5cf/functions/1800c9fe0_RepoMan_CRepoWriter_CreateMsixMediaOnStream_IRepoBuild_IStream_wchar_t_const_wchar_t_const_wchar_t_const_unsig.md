# RepoMan::CRepoWriter::CreateMsixMediaOnStream(IRepoBuild *,IStream *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,IRepoMedia * *)

- ea: `0x1800c9fe0`
- end: `0x1800caabc`
- name: `?CreateMsixMediaOnStream@CRepoWriter@RepoMan@@UEAAJPEAUIRepoBuild@@PEAUIStream@@PEB_W22_K2PEAPEAUIRepoMedia@@@Z`
- size: `2780`
- prototype: `int(RepoMan::CRepoWriter *__hidden this, struct IRepoBuild *, struct IStream *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned __int64, const wchar_t *, struct IRepoMedia **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008770`
- `0x180009368`
- `0x180013b14`
- `0x180022670`
- `0x18002d958`
- `0x18002f9b0`
- `0x18007d930`
- `0x1800c5460`
- `0x1800c5ff4`
- `0x1800c6180`
- `0x1800c9fe0`
- `0x1800caabc`
- `0x1800cabf0`
- `0x18018aed8`
- `0x18018b5f0`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca170`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca392`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca57d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca611`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca6bd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca72b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca9fd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca170`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca392`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca57d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca611`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca6bd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca72b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800ca9fd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca169`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca38b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca576`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca60a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca6b6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca724`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca169`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca38b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca576`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca60a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca6b6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca724`

## string_xrefs

- `0x1800ca756`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800caaa9`: `src\repoman\src\repoman\repowriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall RepoMan::CRepoWriter::CreateMsixMediaOnStream(
        RepoMan::CRepoWriter *this,
        struct IRepoBuild *a2,
        unsigned __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        unsigned __int64 a7,
        const wchar_t *a8,
        struct IRepoMedia **a9)
{
  __int64 v12; // rdi
  __int64 v13; // r8
  void *v14; // rcx
  unsigned __int64 v15; // rbx
  const wchar_t *v16; // rcx
  unsigned __int64 v17; // r14
  size_t v18; // r8
  int v19; // eax
  bool v20; // zf
  int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rbx
  unsigned __int64 v24; // rbx
  __int64 v25; // rcx
  wchar_t *v26; // rcx
  void **v27; // r14
  int v28; // ebx
  __int64 v29; // r8
  __int64 v30; // r13
  __int64 v31; // r8
  int v32; // r12d
  int v33; // eax
  wchar_t *v34; // rcx
  void *v35; // rcx
  __m128i v36; // xmm0
  void *v37; // rcx
  void *v38; // rcx
  RepoMan *v39; // rcx
  const char *v40; // r9
  __int64 v41; // rbx
  _OWORD *v42; // rdx
  __int64 v43; // rbx
  __int64 v44; // rdi
  struct IRepoMedia **MsixMediaForStream; // rax
  struct IRepoMedia *v46; // rcx
  struct IRepoMedia **v47; // rbx
  __int64 v48; // rcx
  struct IRepoMedia *v49; // rbx
  __int64 v50; // rcx
  _QWORD *v51; // rdi
  __int64 v52; // rcx
  int v53; // r8d
  __int64 result; // rax
  char v55; // [rsp+60h] [rbp-1B8h]
  __int64 v56; // [rsp+68h] [rbp-1B0h] BYREF
  void *v57; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v58; // [rsp+78h] [rbp-1A0h] BYREF
  struct IRepoBuild *v59; // [rsp+80h] [rbp-198h] BYREF
  const wchar_t *v60; // [rsp+88h] [rbp-190h]
  const wchar_t *v61; // [rsp+90h] [rbp-188h]
  const wchar_t *v62; // [rsp+98h] [rbp-180h]
  struct IStream *v63; // [rsp+A0h] [rbp-178h]
  const wchar_t *v64; // [rsp+A8h] [rbp-170h]
  struct IRepoMedia **v65; // [rsp+B0h] [rbp-168h]
  wchar_t *S1[2]; // [rsp+B8h] [rbp-160h] BYREF
  __m128i v67; // [rsp+C8h] [rbp-150h]
  void *Block[2]; // [rsp+D8h] [rbp-140h] BYREF
  __m128i v69; // [rsp+E8h] [rbp-130h]
  WCHAR WideCharStr[8]; // [rsp+F8h] [rbp-120h] BYREF
  __m128i v71; // [rsp+108h] [rbp-110h]
  void *v72[2]; // [rsp+118h] [rbp-100h] BYREF
  __m128i si128; // [rsp+128h] [rbp-F0h]
  _QWORD v74[2]; // [rsp+138h] [rbp-E0h] BYREF
  unsigned __int64 v75; // [rsp+148h] [rbp-D0h]
  unsigned __int64 v76; // [rsp+150h] [rbp-C8h]
  CHAR v77[16]; // [rsp+158h] [rbp-C0h] BYREF
  __m128i v78; // [rsp+168h] [rbp-B0h]
  CHAR v79[16]; // [rsp+178h] [rbp-A0h] BYREF
  __m128i v80; // [rsp+188h] [rbp-90h]
  CHAR v81[16]; // [rsp+198h] [rbp-80h] BYREF
  __m128i v82; // [rsp+1A8h] [rbp-70h]
  CHAR MultiByteStr[32]; // [rsp+1B8h] [rbp-60h] BYREF

  v62 = a4;
  v63 = (struct IStream *)a3;
  v59 = a2;
  v61 = a6;
  v60 = a8;
  v64 = a5;
  v65 = a9;
  LODWORD(v56) = 0;
  if ( !a2 || !a3 || !a4 || !*a4 || !a5 || !*a5 || !a6 || !*a6 || !a9 || *a9 )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      101,
      (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
      (unsigned int)"invalid argument(s)",
      -2147024809,
      8);
  *(_OWORD *)Block = 0;
  v69 = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a5[v13] );
  try
  {
    std::wstring::_Construct<1,wchar_t const *>(Block, a5, v13);
    RepoMan::utf16_to_utf8(MultiByteStr, (LPCWCH)Block);
    if ( v69.m128i_i64[1] > 7uLL )
    {
      v14 = Block[0];
      if ( (unsigned __int64)(2 * v69.m128i_i64[1] + 2) >= 0x1000 )
      {
        v14 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v14);
    }
    v55 = RepoMan::CRepoMan::FlightValue(*((_QWORD *)this + 3), 3);
    if ( v55 )
    {
      *(_OWORD *)S1 = 0;
      v67 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(S1, L"C2RClient", 9);
      v15 = -1;
      do
        ++v15;
      while ( a4[v15] );
      v16 = (const wchar_t *)S1;
      if ( v67.m128i_i64[1] > 7uLL )
        v16 = S1[0];
      v17 = v67.m128i_i64[0];
      v18 = v67.m128i_i64[0];
      if ( v15 < v67.m128i_i64[0] )
        v18 = v15;
      v19 = wmemcmp(v16, a4, v18);
      v20 = v19 == 0;
      if ( !v19 )
      {
        if ( v17 >= v15 )
          v21 = v17 > v15;
        else
          v21 = -1;
        v20 = v21 == 0;
      }
      *((_BYTE *)this + 76) = v20;
      *(_QWORD *)WideCharStr = this;
      *(_QWORD *)&WideCharStr[4] = &a7;
      v22 = sub_1800CAABC(WideCharStr, v77);
      if ( (RepoMan::CRepoWriter *)((char *)this + 80) != (RepoMan::CRepoWriter *)v22 )
      {
        std::string::_Tidy_deallocate((char *)this + 80);
        *((_OWORD *)this + 5) = *(_OWORD *)v22;
        *((_OWORD *)this + 6) = *(_OWORD *)(v22 + 16);
        *(_QWORD *)(v22 + 16) = 0;
        *(_QWORD *)(v22 + 24) = 15;
        *(_BYTE *)v22 = 0;
      }
      std::string::_Tidy_deallocate(v77);
      *(_QWORD *)WideCharStr = this;
      *(_QWORD *)&WideCharStr[4] = MultiByteStr;
      v23 = sub_1800CABF0(WideCharStr, v77);
      if ( (RepoMan::CRepoWriter *)((char *)this + 112) != (RepoMan::CRepoWriter *)v23 )
      {
        std::string::_Tidy_deallocate((char *)this + 112);
        *((_OWORD *)this + 7) = *(_OWORD *)v23;
        *((_OWORD *)this + 8) = *(_OWORD *)(v23 + 16);
        *(_QWORD *)(v23 + 16) = 0;
        *(_QWORD *)(v23 + 24) = 15;
        *(_BYTE *)v23 = 0;
      }
      std::string::_Tidy_deallocate(v77);
      v24 = a3 & -(__int64)(*((_BYTE *)this + 76) != 0);
      if ( v24 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v24 + 8LL))(a3 & -(__int64)(*((_BYTE *)this + 76) != 0));
      v25 = *((_QWORD *)this + 18);
      *((_QWORD *)this + 18) = v24;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v67.m128i_i64[1] > 7uLL )
      {
        v26 = S1[0];
        if ( (unsigned __int64)(2 * v67.m128i_i64[1] + 2) >= 0x1000 )
        {
          v26 = (wchar_t *)*((_QWORD *)S1[0] - 1);
          if ( (unsigned __int64)((char *)S1[0] - (char *)v26 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v26);
      }
    }
    if ( v60 )
    {
      *(_OWORD *)Block = 0;
      v69 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v60[v29] );
      std::wstring::_Construct<1,wchar_t const *>(Block, v60, v29);
      v27 = (void **)RepoMan::utf16_to_utf8(v77, (LPCWCH)Block);
      v28 = 6;
    }
    else
    {
      *(_OWORD *)v72 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v72[0]) = 0;
      v27 = v72;
      v28 = 1;
    }
    LODWORD(v56) = v28;
    v30 = a7;
    *(_OWORD *)WideCharStr = 0;
    v71 = 0;
    v31 = -1;
    do
      ++v31;
    while ( v61[v31] );
    std::wstring::_Construct<1,wchar_t const *>(WideCharStr, v61, v31);
    v32 = RepoMan::utf16_to_utf8(v81, WideCharStr);
    *(_OWORD *)S1 = 0;
    v67 = 0;
    do
      ++v12;
    while ( v62[v12] );
    std::wstring::_Construct<1,wchar_t const *>(S1, v62, v12);
    v33 = RepoMan::utf16_to_utf8(v79, (LPCWCH)S1);
    RepoMan::MSIXFormat::MakeMsixPackageFullName(
      (unsigned int)v74,
      v33,
      (unsigned int)MultiByteStr,
      v32,
      v30,
      (__int64)v27);
    std::string::_Tidy_deallocate(v79);
    *(_QWORD *)v79 = 19937;
    v80 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v67.m128i_i64[1] > 7uLL )
    {
      v34 = S1[0];
      if ( (unsigned __int64)(2 * v67.m128i_i64[1] + 2) >= 0x1000 )
      {
        v34 = (wchar_t *)*((_QWORD *)S1[0] - 1);
        if ( (unsigned __int64)((char *)S1[0] - (char *)v34 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v34);
    }
    S1[0] = (wchar_t *)19937;
    v67 = _mm_load_si128((const __m128i *)&_xmm);
    std::string::_Tidy_deallocate(v81);
    *(_QWORD *)v81 = 19937;
    v82 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v71.m128i_i64[1] > 7uLL )
    {
      v35 = *(void **)WideCharStr;
      if ( (unsigned __int64)(2 * v71.m128i_i64[1] + 2) >= 0x1000 )
      {
        v35 = *(void **)(*(_QWORD *)WideCharStr - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)WideCharStr - (_QWORD)v35 - 8LL) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v35);
    }
    *(_QWORD *)WideCharStr = 19937;
    v36 = _mm_load_si128((const __m128i *)&_xmm);
    v71 = v36;
    if ( (v28 & 4) != 0 )
    {
      LOBYTE(v28) = v28 & 0xFB;
      std::string::_Tidy_deallocate(v77);
      *(_QWORD *)v77 = 19937;
      v78 = _mm_load_si128((const __m128i *)&_xmm);
      v36 = _mm_load_si128((const __m128i *)&_xmm);
    }
    if ( (v28 & 2) != 0 )
    {
      LOBYTE(v28) = v28 & 0xFD;
      if ( v69.m128i_i64[1] > 7uLL )
      {
        v37 = Block[0];
        if ( (unsigned __int64)(2 * v69.m128i_i64[1] + 2) >= 0x1000 )
        {
          v37 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v37 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v37);
        v36 = _mm_load_si128((const __m128i *)&_xmm);
      }
      Block[0] = (void *)19937;
      v69 = v36;
    }
    if ( (v28 & 1) != 0 && si128.m128i_i64[1] > 0xFuLL )
    {
      v38 = v72[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v38 = (void *)*((_QWORD *)v72[0] - 1);
        if ( (unsigned __int64)((char *)v72[0] - (char *)v38 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v38);
    }
    v58 = 0;
    v39 = (RepoMan *)(**(unsigned int (__fastcall ***)(RepoMan::CRepoWriter *, GUID *, __int64 *))this)(
                       this,
                       &IID_IRepoWriter,
                       &v58);
    RepoMan::RaiseExceptionIfFailed(v39, 150, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v40);
    *(_OWORD *)v72 = 0;
    si128.m128i_i64[0] = 0;
    si128.m128i_i64[1] = 15;
    LOBYTE(v72[0]) = 0;
    v41 = *((_QWORD *)this + 4);
    v67 = _mm_load_si128((const __m128i *)&_xmm);
    *(_OWORD *)S1 = *(_OWORD *)v72;
    *(_OWORD *)Block = 0;
    v69 = 0;
    v42 = v74;
    if ( v76 > 0xF )
      v42 = (_OWORD *)v74[0];
    std::string::_Construct<2,char const *>(Block, v42, v75);
    LODWORD(v56) = 2;
    *(_QWORD *)WideCharStr = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v59 + 24LL))(v59);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Media,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Media,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::FormatType,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::URI,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::Insert(
      v41 + 9080,
      (unsigned int)&v57,
      (unsigned int)WideCharStr,
      (unsigned int)&v56,
      (__int64)Block,
      (__int64)S1);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v69 = _mm_load_si128((const __m128i *)&_xmm);
    std::string::_Tidy_deallocate(S1);
    RepoMan::CRepoWriter::CacheMediaTags(this, *((_QWORD *)v57 + 10), v74);
    v43 = a7;
    v44 = v58;
    v59 = (struct IRepoBuild *)v63;
    ((void (__fastcall *)(struct IStream *))v63->lpVtbl->AddRef)(v63);
    MsixMediaForStream = (struct IRepoMedia **)RepoMan::MakeMsixMediaForStream(
                                                 (unsigned int)&v56,
                                                 *((_QWORD *)this + 3),
                                                 *((_QWORD *)this + 4),
                                                 (unsigned int)&v57,
                                                 (__int64)&v59,
                                                 v44,
                                                 (__int64)v62,
                                                 (__int64)v64,
                                                 (__int64)v61,
                                                 v43,
                                                 (__int64)v60);
    v46 = *MsixMediaForStream;
    *MsixMediaForStream = 0;
    v47 = v65;
    *v65 = v46;
    v48 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    if ( v59 )
      (*(void (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v59 + 16LL))(v59);
    if ( v55 && *((_BYTE *)this + 76) )
    {
      v49 = *v47;
      if ( v49 )
        (*(void (__fastcall **)(struct IRepoMedia *))(*(_QWORD *)v49 + 8LL))(v49);
      v50 = *((_QWORD *)this + 19);
      *((_QWORD *)this + 19) = v49;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v57;
    if ( v57 )
    {
      std::string::_Tidy_deallocate((char *)v57 + 32);
      v51[4] = 19937;
      v51[6] = 0;
      v51[7] = 31;
      std::string::_Tidy_deallocate(v51);
      *v51 = 19937;
      v51[2] = 0;
      v51[3] = 31;
      free(v51);
    }
    v57 = (void *)19937;
    std::string::_Tidy_deallocate(v72);
    v52 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    std::string::_Tidy_deallocate(v74);
    v74[0] = 19937;
    v75 = 0;
    v76 = 31;
    std::string::_Tidy_deallocate(MultiByteStr);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\repowriter.cpp", (const char *)0xA4, v53);
  }
  return result;
}

```

## disassembly

```asm
0x1800c9fe0  push    rbx
0x1800c9fe2  push    rsi
0x1800c9fe3  push    rdi
0x1800c9fe4  push    r12
0x1800c9fe6  push    r13
0x1800c9fe8  push    r14
0x1800c9fea  push    r15
0x1800c9fec  sub     rsp, 1E0h
0x1800c9ff3  mov     rax, cs:__security_cookie
0x1800c9ffa  xor     rax, rsp
0x1800c9ffd  mov     [rsp+218h+var_40], rax
0x1800ca005  mov     r12, r9
0x1800ca008  mov     [rsp+218h+var_180], r9
0x1800ca010  mov     r13, r8
0x1800ca013  mov     [rsp+218h+var_178], r8
0x1800ca01b  mov     r8, rdx
0x1800ca01e  mov     [rsp+218h+var_198], rdx
0x1800ca026  mov     rsi, rcx
0x1800ca029  mov     rdx, [rsp+218h+arg_28]
0x1800ca031  mov     [rsp+218h+var_188], rdx
0x1800ca039  mov     rax, [rsp+218h+arg_38]
0x1800ca041  mov     [rsp+218h+var_190], rax
0x1800ca049  mov     rax, [rsp+218h+arg_20]
0x1800ca051  mov     [rsp+218h+var_170], rax
0x1800ca059  mov     rcx, [rsp+218h+arg_40]
0x1800ca061  mov     [rsp+218h+var_168], rcx
0x1800ca069  xor     r14d, r14d
0x1800ca06c  mov     dword ptr [rsp+218h+var_1B0], r14d
0x1800ca071  test    r8, r8
0x1800ca074  jz      loc_1800CAA94
0x1800ca07a  test    r13, r13
0x1800ca07d  jz      loc_1800CAA94
0x1800ca083  test    r9, r9
0x1800ca086  jz      loc_1800CAA94
0x1800ca08c  cmp     r14w, [r9]
0x1800ca090  jz      loc_1800CAA94
0x1800ca096  test    rax, rax
0x1800ca099  jz      loc_1800CAA94
0x1800ca09f  cmp     r14w, [rax]
0x1800ca0a3  jz      loc_1800CAA94
0x1800ca0a9  test    rdx, rdx
0x1800ca0ac  jz      loc_1800CAA94
0x1800ca0b2  cmp     r14w, [rdx]
0x1800ca0b6  jz      loc_1800CAA94
0x1800ca0bc  test    rcx, rcx
0x1800ca0bf  jz      loc_1800CAA94
0x1800ca0c5  cmp     [rcx], r14
0x1800ca0c8  jnz     loc_1800CAA94
0x1800ca0ce  xorps   xmm0, xmm0
0x1800ca0d1  movups  xmmword ptr [rsp+218h+Block], xmm0
0x1800ca0d9  xorps   xmm1, xmm1
0x1800ca0dc  movdqu  [rsp+218h+var_130], xmm1
0x1800ca0e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ca0e9  mov     r8, rdi
0x1800ca0ec  inc     r8
0x1800ca0ef  cmp     [rax+r8*2], r14w
0x1800ca0f4  jnz     short loc_1800CA0EC
0x1800ca0f6  mov     rdx, rax
0x1800ca0f9  lea     rcx, [rsp+218h+Block]
0x1800ca101  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ca106  nop
0x1800ca107  lea     rdx, [rsp+218h+Block]; lpWideCharStr
0x1800ca10f  lea     rcx, [rsp+218h+MultiByteStr]; lpMultiByteStr
0x1800ca117  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800ca11c  nop
0x1800ca11d  mov     rax, qword ptr [rsp+218h+var_130+8]
0x1800ca125  mov     r15d, 1000h
0x1800ca12b  cmp     rax, 7
0x1800ca12f  jbe     short loc_1800CA176
0x1800ca131  mov     rcx, [rsp+218h+Block]; Block
0x1800ca139  mov     rdx, rcx
0x1800ca13c  lea     rax, ds:2[rax*2]
0x1800ca144  cmp     rax, r15
0x1800ca147  jb      short loc_1800CA170
0x1800ca149  mov     rcx, [rcx-8]
0x1800ca14d  sub     rdx, rcx
0x1800ca150  lea     rax, [rdx-8]
0x1800ca154  cmp     rax, 1Fh
0x1800ca158  jbe     short loc_1800CA170
0x1800ca15a  mov     [rsp+218h+Reserved], r14; Reserved
0x1800ca15f  xor     r9d, r9d; LineNo
0x1800ca162  xor     r8d, r8d; FileName
0x1800ca165  xor     edx, edx; FunctionName
0x1800ca167  xor     ecx, ecx; Expression
0x1800ca169  call    cs:__imp__invoke_watson
0x1800ca170  call    cs:__imp_free
0x1800ca176  mov     edx, 3
0x1800ca17b  mov     rcx, [rsi+18h]
0x1800ca17f  call    ?FlightValue@CRepoMan@RepoMan@@QEBA_NW4_REPOMAN_FLIGHT@@@Z; RepoMan::CRepoMan::FlightValue(_REPOMAN_FLIGHT)
0x1800ca184  mov     [rsp+218h+var_1B8], al
0x1800ca188  test    al, al
0x1800ca18a  jz      loc_1800CA398
0x1800ca190  xorps   xmm0, xmm0
0x1800ca193  movups  xmmword ptr [rsp+218h+S1], xmm0
0x1800ca19b  mov     qword ptr [rsp+218h+var_150], r14
0x1800ca1a3  mov     qword ptr [rsp+218h+var_150+8], r14
0x1800ca1ab  mov     r8d, 9
0x1800ca1b1  lea     rdx, aC2rclient; "C2RClient"
0x1800ca1b8  lea     rcx, [rsp+218h+S1]
0x1800ca1c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ca1c5  nop
0x1800ca1c6  mov     rbx, rdi
0x1800ca1c9  inc     rbx
0x1800ca1cc  cmp     [r12+rbx*2], r14w
0x1800ca1d1  jnz     short loc_1800CA1C9
0x1800ca1d3  lea     rcx, [rsp+218h+S1]
0x1800ca1db  cmp     qword ptr [rsp+218h+var_150+8], 7
0x1800ca1e4  cmova   rcx, [rsp+218h+S1]; S1
0x1800ca1ed  mov     r14, qword ptr [rsp+218h+var_150]
0x1800ca1f5  mov     r8, r14
0x1800ca1f8  cmp     rbx, r14
0x1800ca1fb  cmovb   r8, rbx; N
0x1800ca1ff  mov     rdx, r12; S2
0x1800ca202  call    wmemcmp
0x1800ca207  xor     r12d, r12d
0x1800ca20a  test    eax, eax
0x1800ca20c  jnz     short loc_1800CA21F
0x1800ca20e  cmp     r14, rbx
0x1800ca211  jnb     short loc_1800CA217
0x1800ca213  mov     eax, edi
0x1800ca215  jmp     short loc_1800CA21D
0x1800ca217  mov     eax, r12d
0x1800ca21a  setnbe  al
0x1800ca21d  test    eax, eax
0x1800ca21f  setz    al
0x1800ca222  mov     [rsi+4Ch], al
0x1800ca225  mov     qword ptr [rsp+218h+WideCharStr], rsi
0x1800ca22d  lea     rax, [rsp+218h+arg_30]
0x1800ca235  mov     qword ptr [rsp+218h+WideCharStr+8], rax
0x1800ca23d  lea     rdx, [rsp+218h+var_C0]
0x1800ca245  lea     rcx, [rsp+218h+WideCharStr]
0x1800ca24d  call    sub_1800CAABC
0x1800ca252  mov     rbx, rax
0x1800ca255  lea     r14, [rsi+50h]
0x1800ca259  cmp     r14, rax
0x1800ca25c  jz      short loc_1800CA285
0x1800ca25e  mov     rcx, r14
0x1800ca261  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ca266  movups  xmm0, xmmword ptr [rbx]
0x1800ca269  movups  xmmword ptr [r14], xmm0
0x1800ca26d  movups  xmm1, xmmword ptr [rbx+10h]
0x1800ca271  movups  xmmword ptr [r14+10h], xmm1
0x1800ca276  mov     [rbx+10h], r12
0x1800ca27a  mov     qword ptr [rbx+18h], 0Fh
0x1800ca282  mov     [rbx], r12b
0x1800ca285  lea     rcx, [rsp+218h+var_C0]
0x1800ca28d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ca292  mov     qword ptr [rsp+218h+WideCharStr], rsi
0x1800ca29a  lea     rax, [rsp+218h+MultiByteStr]
0x1800ca2a2  mov     qword ptr [rsp+218h+WideCharStr+8], rax
0x1800ca2aa  lea     rdx, [rsp+218h+var_C0]
0x1800ca2b2  lea     rcx, [rsp+218h+WideCharStr]
0x1800ca2ba  call    sub_1800CABF0
0x1800ca2bf  mov     rbx, rax
0x1800ca2c2  lea     r14, [rsi+70h]
0x1800ca2c6  cmp     r14, rax
0x1800ca2c9  jz      short loc_1800CA2F7
0x1800ca2cb  mov     rcx, r14
0x1800ca2ce  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ca2d3  movups  xmm0, xmmword ptr [rbx]
0x1800ca2d6  movups  xmmword ptr [r14], xmm0
0x1800ca2da  movups  xmm1, xmmword ptr [rbx+10h]
0x1800ca2de  movups  xmmword ptr [r14+10h], xmm1
0x1800ca2e3  xor     r14d, r14d
0x1800ca2e6  mov     [rbx+10h], r14
0x1800ca2ea  mov     qword ptr [rbx+18h], 0Fh
0x1800ca2f2  mov     [rbx], r14b
0x1800ca2f5  jmp     short loc_1800CA2FA
0x1800ca2f7  xor     r14d, r14d
0x1800ca2fa  lea     rcx, [rsp+218h+var_C0]
0x1800ca302  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ca307  mov     al, [rsi+4Ch]
0x1800ca30a  neg     al
0x1800ca30c  sbb     rbx, rbx
0x1800ca30f  and     rbx, r13
0x1800ca312  jz      short loc_1800CA324
0x1800ca314  mov     rax, [rbx]
0x1800ca317  mov     rcx, rbx
0x1800ca31a  mov     rax, [rax+8]
0x1800ca31e  call    cs:__guard_dispatch_icall_fptr
0x1800ca324  mov     rcx, [rsi+90h]
0x1800ca32b  mov     [rsi+90h], rbx
0x1800ca332  test    rcx, rcx
0x1800ca335  jz      short loc_1800CA345
0x1800ca337  mov     rax, [rcx]
0x1800ca33a  mov     rax, [rax+10h]
0x1800ca33e  call    cs:__guard_dispatch_icall_fptr
0x1800ca344  nop
0x1800ca345  mov     rax, qword ptr [rsp+218h+var_150+8]
0x1800ca34d  cmp     rax, 7
0x1800ca351  jbe     short loc_1800CA398
0x1800ca353  mov     rcx, [rsp+218h+S1]; Block
0x1800ca35b  mov     rdx, rcx
0x1800ca35e  lea     rax, ds:2[rax*2]
0x1800ca366  cmp     rax, r15
0x1800ca369  jb      short loc_1800CA392
0x1800ca36b  mov     rcx, [rcx-8]
0x1800ca36f  sub     rdx, rcx
0x1800ca372  lea     rax, [rdx-8]
0x1800ca376  cmp     rax, 1Fh
0x1800ca37a  jbe     short loc_1800CA392
0x1800ca37c  mov     [rsp+218h+Reserved], r14; Reserved
0x1800ca381  xor     r9d, r9d; LineNo
0x1800ca384  xor     r8d, r8d; FileName
0x1800ca387  xor     edx, edx; FunctionName
0x1800ca389  xor     ecx, ecx; Expression
0x1800ca38b  call    cs:__imp__invoke_watson
0x1800ca392  call    cs:__imp_free
0x1800ca398  mov     rax, [rsp+218h+var_190]
0x1800ca3a0  xorps   xmm0, xmm0
0x1800ca3a3  test    rax, rax
0x1800ca3a6  jnz     short loc_1800CA3D6
0x1800ca3a8  movups  xmmword ptr [rsp+218h+var_100], xmm0
0x1800ca3b0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800ca3b8  movdqu  [rsp+218h+var_F0], xmm0
0x1800ca3c1  mov     byte ptr [rsp+218h+var_100], r14b
0x1800ca3c9  lea     r14, [rsp+218h+var_100]
0x1800ca3d1  lea     ebx, [rax+1]
0x1800ca3d4  jmp     short loc_1800CA425
0x1800ca3d6  movups  xmmword ptr [rsp+218h+Block], xmm0
0x1800ca3de  xorps   xmm1, xmm1
0x1800ca3e1  movdqu  [rsp+218h+var_130], xmm1
0x1800ca3ea  mov     r8, rdi
0x1800ca3ed  inc     r8
0x1800ca3f0  cmp     [rax+r8*2], r14w
0x1800ca3f5  jnz     short loc_1800CA3ED
0x1800ca3f7  mov     rdx, rax
0x1800ca3fa  lea     rcx, [rsp+218h+Block]
0x1800ca402  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ca407  nop
0x1800ca408  lea     rdx, [rsp+218h+Block]; lpWideCharStr
0x1800ca410  lea     rcx, [rsp+218h+var_C0]; lpMultiByteStr
0x1800ca418  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800ca41d  mov     r14, rax
0x1800ca420  mov     ebx, 6
0x1800ca425  mov     dword ptr [rsp+218h+var_1B0], ebx
0x1800ca429  mov     r13, [rsp+218h+arg_30]
0x1800ca431  xorps   xmm0, xmm0
0x1800ca434  movups  xmmword ptr [rsp+218h+WideCharStr], xmm0
0x1800ca43c  xorps   xmm1, xmm1
0x1800ca43f  movdqu  [rsp+218h+var_110], xmm1
0x1800ca448  mov     r8, rdi
0x1800ca44b  mov     rax, [rsp+218h+var_188]
0x1800ca453  xor     ecx, ecx
0x1800ca455  inc     r8
0x1800ca458  cmp     [rax+r8*2], cx
0x1800ca45d  jnz     short loc_1800CA455
0x1800ca45f  mov     rdx, rax
0x1800ca462  lea     rcx, [rsp+218h+WideCharStr]
0x1800ca46a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ca46f  nop
0x1800ca470  lea     rdx, [rsp+218h+WideCharStr]; lpWideCharStr
0x1800ca478  lea     rcx, [rsp+218h+var_80]; lpMultiByteStr
0x1800ca480  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800ca485  mov     r12, rax
0x1800ca488  xorps   xmm0, xmm0
0x1800ca48b  movups  xmmword ptr [rsp+218h+S1], xmm0
0x1800ca493  xorps   xmm1, xmm1
0x1800ca496  movdqu  [rsp+218h+var_150], xmm1
0x1800ca49f  mov     rax, [rsp+218h+var_180]
0x1800ca4a7  xor     ecx, ecx
0x1800ca4a9  inc     rdi
0x1800ca4ac  cmp     [rax+rdi*2], cx
0x1800ca4b0  jnz     short loc_1800CA4A9
0x1800ca4b2  mov     r8, rdi
0x1800ca4b5  mov     rdx, rax
0x1800ca4b8  lea     rcx, [rsp+218h+S1]
0x1800ca4c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ca4c5  nop
0x1800ca4c6  lea     rdx, [rsp+218h+S1]; lpWideCharStr
0x1800ca4ce  lea     rcx, [rsp+218h+var_A0]; lpMultiByteStr
0x1800ca4d6  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800ca4db  nop
0x1800ca4dc  mov     [rsp+218h+var_1F0], r14
0x1800ca4e1  mov     [rsp+218h+Reserved], r13
0x1800ca4e6  mov     r9, r12
0x1800ca4e9  lea     r8, [rsp+218h+MultiByteStr]
0x1800ca4f1  mov     rdx, rax
0x1800ca4f4  lea     rcx, [rsp+218h+var_E0]
0x1800ca4fc  call    ?MakeMsixPackageFullName@MSIXFormat@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@00_J0@Z; RepoMan::MSIXFormat::MakeMsixPackageFullName(std::string const &,std::string const &,std::string const &,__int64,std::string const &)
0x1800ca501  nop
0x1800ca502  lea     rcx, [rsp+218h+var_A0]
0x1800ca50a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ca50f  mov     r12d, 4DE1h
0x1800ca515  mov     qword ptr [rsp+218h+var_A0], r12
0x1800ca51d  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800ca525  movdqu  [rsp+218h+var_90], xmm0
0x1800ca52e  mov     rax, qword ptr [rsp+218h+var_150+8]
0x1800ca536  cmp     rax, 7
0x1800ca53a  jbe     short loc_1800CA583
0x1800ca53c  mov     rcx, [rsp+218h+S1]; Block
0x1800ca544  mov     rdx, rcx
0x1800ca547  lea     rax, ds:2[rax*2]
0x1800ca54f  cmp     rax, r15
0x1800ca552  jb      short loc_1800CA57D
0x1800ca554  mov     rcx, [rcx-8]
0x1800ca558  sub     rdx, rcx
0x1800ca55b  lea     rax, [rdx-8]
0x1800ca55f  cmp     rax, 1Fh
0x1800ca563  jbe     short loc_1800CA57D
  ... truncated ...
```
