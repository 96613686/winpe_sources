# RepoMan::CRepoWriter::CreateCellularMediaOnStream(IRepoBuild *,IStream *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,IRepoMedia * *)

- ea: `0x1800d00d0`
- end: `0x1800d0a27`
- name: `?CreateCellularMediaOnStream@CRepoWriter@RepoMan@@UEAAJPEAUIRepoBuild@@PEAUIStream@@PEB_W22_K2PEAPEAUIRepoMedia@@@Z`
- size: `2391`
- prototype: `__int64 __fastcall(RepoMan::CRepoWriter *__hidden this, struct IRepoBuild *, struct IStream *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned __int64, const wchar_t *, struct IRepoMedia **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001504`
- `0x180013b14`
- `0x1800220e4`
- `0x180022670`
- `0x18002d958`
- `0x18002f9b0`
- `0x18003386c`
- `0x18007d930`
- `0x1800c5ff4`
- `0x1800c62d8`
- `0x1800d00d0`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b5f0`
- `0x18019a840`
- `0x18019f7a0`
- `0x18019f800`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800d07ea`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800d07ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0261`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0433`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d04c7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0573`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d05e5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d07fe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d086b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0261`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0433`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d04c7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d0573`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d05e5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d07fe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d086b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d025a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d042c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d04c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d056c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d05de`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d07d4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d0864`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d025a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d042c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d04c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d056c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d05de`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d07d4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d0864`

## string_xrefs

- `0x1800d0614`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800d0a14`: `src\repoman\src\repoman\repowriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall RepoMan::CRepoWriter::CreateCellularMediaOnStream(
        RepoMan::CRepoWriter *this,
        struct IRepoBuild *a2,
        struct IStream *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        unsigned __int64 a7,
        const wchar_t *a8,
        struct IRepoMedia **a9)
{
  __int64 v10; // rdi
  __int64 v11; // r8
  void *v12; // rcx
  void **v13; // rsi
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r8
  int v17; // r15d
  int v18; // eax
  void *v19; // rcx
  void *v20; // rcx
  __m128i v21; // xmm0
  void *v22; // rcx
  void *v23; // rcx
  RepoMan *v24; // rcx
  const char *v25; // r9
  __int64 v26; // r12
  unsigned __int64 v27; // rsi
  void **v28; // r15
  __int64 v29; // rdi
  size_t v30; // rcx
  void *v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  RepoMan::CRepoWriter *v34; // rbx
  struct IRepoMedia **MsixMediaForStream; // rax
  struct IRepoMedia *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // r8d
  __int64 result; // rax
  int v41; // [rsp+60h] [rbp-1C8h] BYREF
  RepoMan::CRepoWriter *v42; // [rsp+68h] [rbp-1C0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-1B8h] BYREF
  __int64 v44; // [rsp+78h] [rbp-1B0h] BYREF
  __int64 v45; // [rsp+80h] [rbp-1A8h] BYREF
  struct IRepoBuild *v46; // [rsp+88h] [rbp-1A0h]
  __int64 v47; // [rsp+90h] [rbp-198h] BYREF
  struct IStream *v48; // [rsp+98h] [rbp-190h]
  const wchar_t *v49; // [rsp+A0h] [rbp-188h]
  const wchar_t *v50; // [rsp+A8h] [rbp-180h]
  const wchar_t *v51; // [rsp+B0h] [rbp-178h]
  struct IRepoMedia **v52; // [rsp+B8h] [rbp-170h]
  WCHAR v53[8]; // [rsp+C0h] [rbp-168h] BYREF
  __m128i v54; // [rsp+D0h] [rbp-158h]
  void *Block[2]; // [rsp+E0h] [rbp-148h] BYREF
  __m128i v56; // [rsp+F0h] [rbp-138h]
  void *v57[2]; // [rsp+100h] [rbp-128h] BYREF
  __m128i si128; // [rsp+110h] [rbp-118h]
  void *Src[2]; // [rsp+120h] [rbp-108h] BYREF
  unsigned __int64 v60; // [rsp+130h] [rbp-F8h]
  unsigned __int64 v61; // [rsp+138h] [rbp-F0h]
  WCHAR WideCharStr[8]; // [rsp+140h] [rbp-E8h] BYREF
  __m128i v63; // [rsp+150h] [rbp-D8h]
  CHAR v64[16]; // [rsp+160h] [rbp-C8h] BYREF
  __m128i v65; // [rsp+170h] [rbp-B8h]
  CHAR v66[16]; // [rsp+180h] [rbp-A8h] BYREF
  __m128i v67; // [rsp+190h] [rbp-98h]
  CHAR v68[16]; // [rsp+1A0h] [rbp-88h] BYREF
  __m128i v69; // [rsp+1B0h] [rbp-78h]
  CHAR MultiByteStr[32]; // [rsp+1C0h] [rbp-68h] BYREF

  try
  {
    v51 = a4;
    v48 = a3;
    v46 = a2;
    v42 = this;
    v50 = a6;
    v49 = a8;
    v43 = a7;
    v52 = a9;
    v41 = 0;
    if ( !a2 || !a3 || !a4 || !*a4 || !a5 || !*a5 || !a6 || !*a6 || !a9 || *a9 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        654,
        (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
        (unsigned int)"invalid argument(s)",
        -2147024809,
        8);
    *(_OWORD *)Block = 0;
    v56 = 0;
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a5[v11] );
    std::wstring::_Construct<1,wchar_t const *>(Block, a5, v11);
    RepoMan::utf16_to_utf8(MultiByteStr, (LPCWCH)Block);
    if ( v56.m128i_i64[1] > 7uLL )
    {
      v12 = Block[0];
      if ( (unsigned __int64)(2 * v56.m128i_i64[1] + 2) >= 0x1000 )
      {
        v12 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v12);
    }
    if ( a8 )
    {
      *(_OWORD *)Block = 0;
      v56 = 0;
      v15 = -1;
      do
        ++v15;
      while ( a8[v15] );
      std::wstring::_Construct<1,wchar_t const *>(Block, a8, v15);
      v13 = (void **)RepoMan::utf16_to_utf8(v68, (LPCWCH)Block);
      v14 = 6;
    }
    else
    {
      *(_OWORD *)v57 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v57[0]) = 0;
      v13 = v57;
      v14 = 1;
    }
    v41 = v14;
    *(_OWORD *)WideCharStr = 0;
    v63 = 0;
    v16 = -1;
    do
      ++v16;
    while ( a6[v16] );
    std::wstring::_Construct<1,wchar_t const *>(WideCharStr, a6, v16);
    v17 = RepoMan::utf16_to_utf8(v66, WideCharStr);
    *(_OWORD *)v53 = 0;
    v54 = 0;
    do
      ++v10;
    while ( a4[v10] );
    std::wstring::_Construct<1,wchar_t const *>(v53, a4, v10);
    v18 = RepoMan::utf16_to_utf8(v64, v53);
    RepoMan::MSIXFormat::MakeMsixPackageFamilyName(
      (unsigned int)Src,
      v18,
      (unsigned int)MultiByteStr,
      v17,
      v43,
      (__int64)v13);
    std::string::_Tidy_deallocate(v64);
    *(_QWORD *)v64 = 19937;
    v65 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v54.m128i_i64[1] > 7uLL )
    {
      v19 = *(void **)v53;
      if ( (unsigned __int64)(2 * v54.m128i_i64[1] + 2) >= 0x1000 )
      {
        v19 = *(void **)(*(_QWORD *)v53 - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)v53 - (_QWORD)v19 - 8LL) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v19);
    }
    *(_QWORD *)v53 = 19937;
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    std::string::_Tidy_deallocate(v66);
    *(_QWORD *)v66 = 19937;
    v67 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v63.m128i_i64[1] > 7uLL )
    {
      v20 = *(void **)WideCharStr;
      if ( (unsigned __int64)(2 * v63.m128i_i64[1] + 2) >= 0x1000 )
      {
        v20 = *(void **)(*(_QWORD *)WideCharStr - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)WideCharStr - (_QWORD)v20 - 8LL) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v20);
    }
    *(_QWORD *)WideCharStr = 19937;
    v21 = _mm_load_si128((const __m128i *)&_xmm);
    v63 = v21;
    if ( (v14 & 4) != 0 )
    {
      LOBYTE(v14) = v14 & 0xFB;
      std::string::_Tidy_deallocate(v68);
      *(_QWORD *)v68 = 19937;
      v69 = _mm_load_si128((const __m128i *)&_xmm);
      v21 = _mm_load_si128((const __m128i *)&_xmm);
    }
    if ( (v14 & 2) != 0 )
    {
      LOBYTE(v14) = v14 & 0xFD;
      if ( v56.m128i_i64[1] > 7uLL )
      {
        v22 = Block[0];
        if ( (unsigned __int64)(2 * v56.m128i_i64[1] + 2) >= 0x1000 )
        {
          v22 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v22 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v22);
        v21 = _mm_load_si128((const __m128i *)&_xmm);
      }
      Block[0] = (void *)19937;
      v56 = v21;
    }
    if ( (v14 & 1) != 0 && si128.m128i_i64[1] > 0xFuLL )
    {
      v23 = v57[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v23 = (void *)*((_QWORD *)v57[0] - 1);
        if ( (unsigned __int64)((char *)v57[0] - (char *)v23 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v23);
    }
    v44 = 0;
    v24 = (RepoMan *)(**(unsigned int (__fastcall ***)(RepoMan::CRepoWriter *, GUID *, __int64 *))v42)(
                       v42,
                       &IID_IRepoWriter,
                       &v44);
    RepoMan::RaiseExceptionIfFailed(v24, 661, (int)"src\\repoman\\src\\repoman\\repowriter.cpp", v25);
    *(_OWORD *)Block = 0;
    v56.m128i_i64[0] = 0;
    v56.m128i_i64[1] = 15;
    LOBYTE(Block[0]) = 0;
    v26 = *((_QWORD *)v42 + 4);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(_OWORD *)v57 = *(_OWORD *)Block;
    *(_OWORD *)v53 = 0;
    v54 = 0;
    v27 = v60;
    v28 = Src;
    if ( v61 > 0xF )
      v28 = (void **)Src[0];
    v29 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v60 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v60 > 0xF )
    {
      if ( (v60 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
      {
        v29 = v60 | 0xF;
        if ( (v60 | 0xF) < 0x16 )
          v29 = 22;
      }
      v30 = v29 + 1;
      if ( v29 == -1 )
      {
        v31 = 0;
      }
      else if ( v30 < 0x1000 )
      {
        v31 = malloc(v30);
        if ( !v31 )
          std::_Xbad_alloc();
      }
      else
      {
        v31 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v30);
      }
      *(_QWORD *)v53 = v31;
      v54.m128i_i64[0] = v27;
      v54.m128i_i64[1] = v29;
      memmove(v31, v28, v27 + 1);
    }
    else
    {
      v54.m128i_i64[0] = v60;
      v54.m128i_i64[1] = 15;
      *(_OWORD *)v53 = *(_OWORD *)v28;
    }
    v41 = 2;
    v47 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v46 + 24LL))(v46);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Media,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Media,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Media_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Media,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::FormatType,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::URI,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::Insert(
      v26 + 9080,
      (unsigned int)&v45,
      (unsigned int)&v47,
      (unsigned int)&v41,
      (__int64)v53,
      (__int64)v57);
    if ( v54.m128i_i64[1] > 0xFuLL )
    {
      v32 = *(void **)v53;
      if ( (unsigned __int64)(v54.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = *(void **)(*(_QWORD *)v53 - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)v53 - (_QWORD)v32 - 8LL) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    *(_QWORD *)v53 = 19937;
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v33 = v57[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v33 = (void *)*((_QWORD *)v57[0] - 1);
        if ( (unsigned __int64)((char *)v57[0] - (char *)v33 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v33);
    }
    v34 = v42;
    RepoMan::CRepoWriter::CacheMediaTags(v42, *(_QWORD *)(v45 + 80), Src);
    v42 = (RepoMan::CRepoWriter *)v48;
    ((void (__fastcall *)(struct IStream *))v48->lpVtbl->AddRef)(v48);
    MsixMediaForStream = (struct IRepoMedia **)RepoMan::MakeMsixMediaForStream(
                                                 (unsigned int)&v43,
                                                 *((_QWORD *)v34 + 3),
                                                 *((_QWORD *)v34 + 4),
                                                 (unsigned int)&v45,
                                                 (__int64)&v42,
                                                 v44,
                                                 (__int64)v51,
                                                 (__int64)a5,
                                                 (__int64)v50,
                                                 v43,
                                                 (__int64)v49);
    v36 = *MsixMediaForStream;
    *MsixMediaForStream = 0;
    *v52 = v36;
    v37 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    if ( v42 )
      (*(void (__fastcall **)(RepoMan::CRepoWriter *))(*(_QWORD *)v42 + 16LL))(v42);
    __1__unique_ptr_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__QEAA_XZ(&v45);
    std::string::_Tidy_deallocate(Block);
    v38 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    std::string::_Tidy_deallocate(Src);
    Src[0] = (void *)19937;
    v60 = 0;
    v61 = 31;
    std::string::_Tidy_deallocate(MultiByteStr);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\repowriter.cpp", (const char *)0x29E, v39);
  }
  return result;
}

```

## disassembly

```asm
0x1800d00d0  push    rbx
0x1800d00d2  push    rsi
0x1800d00d3  push    rdi
0x1800d00d4  push    r12
0x1800d00d6  push    r13
0x1800d00d8  push    r14
0x1800d00da  push    r15
0x1800d00dc  sub     rsp, 1F0h
0x1800d00e3  mov     rax, cs:__security_cookie
0x1800d00ea  xor     rax, rsp
0x1800d00ed  mov     [rsp+228h+var_48], rax
0x1800d00f5  mov     r12, r9
0x1800d00f8  mov     [rsp+228h+var_178], r9
0x1800d0100  mov     [rsp+228h+var_190], r8
0x1800d0108  mov     [rsp+228h+var_1A0], rdx
0x1800d0110  mov     [rsp+228h+var_1C0], rcx
0x1800d0115  mov     r15, [rsp+228h+arg_28]
0x1800d011d  mov     [rsp+228h+var_180], r15
0x1800d0125  mov     rbx, [rsp+228h+arg_38]
0x1800d012d  mov     [rsp+228h+var_188], rbx
0x1800d0135  mov     r13, [rsp+228h+arg_20]
0x1800d013d  mov     rax, [rsp+228h+arg_30]
0x1800d0145  mov     [rsp+228h+var_1B8], rax
0x1800d014a  mov     rax, [rsp+228h+arg_40]
0x1800d0152  mov     [rsp+228h+var_170], rax
0x1800d015a  xor     esi, esi
0x1800d015c  mov     [rsp+228h+var_1C8], esi
0x1800d0160  test    rdx, rdx
0x1800d0163  jz      loc_1800D09FF
0x1800d0169  test    r8, r8
0x1800d016c  jz      loc_1800D09FF
0x1800d0172  test    r9, r9
0x1800d0175  jz      loc_1800D09FF
0x1800d017b  cmp     si, [r9]
0x1800d017f  jz      loc_1800D09FF
0x1800d0185  test    r13, r13
0x1800d0188  jz      loc_1800D09FF
0x1800d018e  cmp     si, [r13+0]
0x1800d0193  jz      loc_1800D09FF
0x1800d0199  test    r15, r15
0x1800d019c  jz      loc_1800D09FF
0x1800d01a2  cmp     si, [r15]
0x1800d01a6  jz      loc_1800D09FF
0x1800d01ac  test    rax, rax
0x1800d01af  jz      loc_1800D09FF
0x1800d01b5  cmp     [rax], rsi
0x1800d01b8  jnz     loc_1800D09FF
0x1800d01be  xorps   xmm0, xmm0
0x1800d01c1  movups  xmmword ptr [rsp+228h+Block], xmm0
0x1800d01c9  xorps   xmm1, xmm1
0x1800d01cc  movdqu  [rsp+228h+var_138], xmm1
0x1800d01d5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d01d9  mov     r8, rdi
0x1800d01dc  inc     r8
0x1800d01df  cmp     [r13+r8*2+0], si
0x1800d01e5  jnz     short loc_1800D01DC
0x1800d01e7  mov     rdx, r13
0x1800d01ea  lea     rcx, [rsp+228h+Block]
0x1800d01f2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d01f7  nop
0x1800d01f8  lea     rdx, [rsp+228h+Block]; lpWideCharStr
0x1800d0200  lea     rcx, [rsp+228h+MultiByteStr]; lpMultiByteStr
0x1800d0208  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800d020d  nop
0x1800d020e  mov     rax, qword ptr [rsp+228h+var_138+8]
0x1800d0216  mov     r14d, 1000h
0x1800d021c  cmp     rax, 7
0x1800d0220  jbe     short loc_1800D0267
0x1800d0222  mov     rcx, [rsp+228h+Block]; Block
0x1800d022a  mov     rdx, rcx
0x1800d022d  lea     rax, ds:2[rax*2]
0x1800d0235  cmp     rax, r14
0x1800d0238  jb      short loc_1800D0261
0x1800d023a  mov     rcx, [rcx-8]
0x1800d023e  sub     rdx, rcx
0x1800d0241  lea     rax, [rdx-8]
0x1800d0245  cmp     rax, 1Fh
0x1800d0249  jbe     short loc_1800D0261
0x1800d024b  mov     [rsp+228h+Reserved], rsi; Reserved
0x1800d0250  xor     r9d, r9d; LineNo
0x1800d0253  xor     r8d, r8d; FileName
0x1800d0256  xor     edx, edx; FunctionName
0x1800d0258  xor     ecx, ecx; Expression
0x1800d025a  call    cs:__imp__invoke_watson
0x1800d0261  call    cs:__imp_free
0x1800d0267  xorps   xmm0, xmm0
0x1800d026a  test    rbx, rbx
0x1800d026d  jnz     short loc_1800D029F
0x1800d026f  movups  xmmword ptr [rsp+228h+var_128], xmm0
0x1800d0277  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d027f  movdqu  [rsp+228h+var_118], xmm0
0x1800d0288  mov     byte ptr [rsp+228h+var_128], sil
0x1800d0290  lea     rsi, [rsp+228h+var_128]
0x1800d0298  mov     ebx, 1
0x1800d029d  jmp     short loc_1800D02EE
0x1800d029f  movups  xmmword ptr [rsp+228h+Block], xmm0
0x1800d02a7  xorps   xmm1, xmm1
0x1800d02aa  movdqu  [rsp+228h+var_138], xmm1
0x1800d02b3  mov     r8, rdi
0x1800d02b6  inc     r8
0x1800d02b9  cmp     [rbx+r8*2], si
0x1800d02be  jnz     short loc_1800D02B6
0x1800d02c0  mov     rdx, rbx
0x1800d02c3  lea     rcx, [rsp+228h+Block]
0x1800d02cb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d02d0  nop
0x1800d02d1  lea     rdx, [rsp+228h+Block]; lpWideCharStr
0x1800d02d9  lea     rcx, [rsp+228h+var_88]; lpMultiByteStr
0x1800d02e1  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800d02e6  mov     rsi, rax
0x1800d02e9  mov     ebx, 6
0x1800d02ee  mov     [rsp+228h+var_1C8], ebx
0x1800d02f2  xorps   xmm0, xmm0
0x1800d02f5  movups  xmmword ptr [rsp+228h+WideCharStr], xmm0
0x1800d02fd  xorps   xmm1, xmm1
0x1800d0300  movdqu  [rsp+228h+var_D8], xmm1
0x1800d0309  mov     r8, rdi
0x1800d030c  xor     ecx, ecx
0x1800d030e  inc     r8
0x1800d0311  cmp     [r15+r8*2], cx
0x1800d0316  jnz     short loc_1800D030E
0x1800d0318  mov     rdx, r15
0x1800d031b  lea     rcx, [rsp+228h+WideCharStr]
0x1800d0323  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d0328  nop
0x1800d0329  lea     rdx, [rsp+228h+WideCharStr]; lpWideCharStr
0x1800d0331  lea     rcx, [rsp+228h+var_A8]; lpMultiByteStr
0x1800d0339  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800d033e  mov     r15, rax
0x1800d0341  xorps   xmm0, xmm0
0x1800d0344  movups  xmmword ptr [rsp+228h+var_168], xmm0
0x1800d034c  xorps   xmm1, xmm1
0x1800d034f  movdqu  [rsp+228h+var_158], xmm1
0x1800d0358  xor     eax, eax
0x1800d035a  inc     rdi
0x1800d035d  cmp     [r12+rdi*2], ax
0x1800d0362  jnz     short loc_1800D035A
0x1800d0364  mov     r8, rdi
0x1800d0367  mov     rdx, r12
0x1800d036a  lea     rcx, [rsp+228h+var_168]
0x1800d0372  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d0377  nop
0x1800d0378  lea     rdx, [rsp+228h+var_168]; lpWideCharStr
0x1800d0380  lea     rcx, [rsp+228h+var_C8]; lpMultiByteStr
0x1800d0388  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800d038d  nop
0x1800d038e  mov     [rsp+228h+var_200], rsi
0x1800d0393  mov     rcx, [rsp+228h+var_1B8]
0x1800d0398  mov     [rsp+228h+Reserved], rcx
0x1800d039d  mov     r9, r15
0x1800d03a0  lea     r8, [rsp+228h+MultiByteStr]
0x1800d03a8  mov     rdx, rax
0x1800d03ab  lea     rcx, [rsp+228h+Src]
0x1800d03b3  call    ?MakeMsixPackageFamilyName@MSIXFormat@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@00_J0@Z; RepoMan::MSIXFormat::MakeMsixPackageFamilyName(std::string const &,std::string const &,std::string const &,__int64,std::string const &)
0x1800d03b8  nop
0x1800d03b9  lea     rcx, [rsp+228h+var_C8]
0x1800d03c1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d03c6  mov     edi, 4DE1h
0x1800d03cb  mov     qword ptr [rsp+228h+var_C8], rdi
0x1800d03d3  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800d03db  movdqu  [rsp+228h+var_B8], xmm0
0x1800d03e4  mov     rax, qword ptr [rsp+228h+var_158+8]
0x1800d03ec  cmp     rax, 7
0x1800d03f0  jbe     short loc_1800D0439
0x1800d03f2  mov     rcx, qword ptr [rsp+228h+var_168]; Block
0x1800d03fa  mov     rdx, rcx
0x1800d03fd  lea     rax, ds:2[rax*2]
0x1800d0405  cmp     rax, r14
0x1800d0408  jb      short loc_1800D0433
0x1800d040a  mov     rcx, [rcx-8]
0x1800d040e  sub     rdx, rcx
0x1800d0411  lea     rax, [rdx-8]
0x1800d0415  cmp     rax, 1Fh
0x1800d0419  jbe     short loc_1800D0433
0x1800d041b  xor     eax, eax
0x1800d041d  mov     [rsp+228h+Reserved], rax; Reserved
0x1800d0422  xor     r9d, r9d; LineNo
0x1800d0425  xor     r8d, r8d; FileName
0x1800d0428  xor     edx, edx; FunctionName
0x1800d042a  xor     ecx, ecx; Expression
0x1800d042c  call    cs:__imp__invoke_watson
0x1800d0433  call    cs:__imp_free
0x1800d0439  mov     qword ptr [rsp+228h+var_168], rdi
0x1800d0441  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d0449  movdqu  [rsp+228h+var_158], xmm0
0x1800d0452  lea     rcx, [rsp+228h+var_A8]
0x1800d045a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d045f  mov     qword ptr [rsp+228h+var_A8], rdi
0x1800d0467  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800d046f  movdqu  [rsp+228h+var_98], xmm0
0x1800d0478  mov     rax, qword ptr [rsp+228h+var_D8+8]
0x1800d0480  cmp     rax, 7
0x1800d0484  jbe     short loc_1800D04CD
0x1800d0486  mov     rcx, qword ptr [rsp+228h+WideCharStr]; Block
0x1800d048e  mov     rdx, rcx
0x1800d0491  lea     rax, ds:2[rax*2]
0x1800d0499  cmp     rax, r14
0x1800d049c  jb      short loc_1800D04C7
0x1800d049e  mov     rcx, [rcx-8]
0x1800d04a2  sub     rdx, rcx
0x1800d04a5  lea     rax, [rdx-8]
0x1800d04a9  cmp     rax, 1Fh
0x1800d04ad  jbe     short loc_1800D04C7
0x1800d04af  xor     eax, eax
0x1800d04b1  mov     [rsp+228h+Reserved], rax; Reserved
0x1800d04b6  xor     r9d, r9d; LineNo
0x1800d04b9  xor     r8d, r8d; FileName
0x1800d04bc  xor     edx, edx; FunctionName
0x1800d04be  xor     ecx, ecx; Expression
0x1800d04c0  call    cs:__imp__invoke_watson
0x1800d04c7  call    cs:__imp_free
0x1800d04cd  mov     qword ptr [rsp+228h+WideCharStr], rdi
0x1800d04d5  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d04dd  movdqu  [rsp+228h+var_D8], xmm0
0x1800d04e6  test    bl, 4
0x1800d04e9  jz      short loc_1800D051C
0x1800d04eb  and     ebx, 0FFFFFFFBh
0x1800d04ee  lea     rcx, [rsp+228h+var_88]
0x1800d04f6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d04fb  mov     qword ptr [rsp+228h+var_88], rdi
0x1800d0503  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800d050b  movdqu  [rsp+228h+var_78], xmm0
0x1800d0514  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d051c  test    bl, 2
0x1800d051f  jz      short loc_1800D0592
0x1800d0521  and     ebx, 0FFFFFFFDh
0x1800d0524  mov     rax, qword ptr [rsp+228h+var_138+8]
0x1800d052c  cmp     rax, 7
0x1800d0530  jbe     short loc_1800D0581
0x1800d0532  mov     rcx, [rsp+228h+Block]; Block
0x1800d053a  mov     rdx, rcx
0x1800d053d  lea     rax, ds:2[rax*2]
0x1800d0545  cmp     rax, r14
0x1800d0548  jb      short loc_1800D0573
0x1800d054a  mov     rcx, [rcx-8]
0x1800d054e  sub     rdx, rcx
0x1800d0551  lea     rax, [rdx-8]
0x1800d0555  cmp     rax, 1Fh
0x1800d0559  jbe     short loc_1800D0573
0x1800d055b  xor     eax, eax
0x1800d055d  mov     [rsp+228h+Reserved], rax; Reserved
0x1800d0562  xor     r9d, r9d; LineNo
0x1800d0565  xor     r8d, r8d; FileName
0x1800d0568  xor     edx, edx; FunctionName
0x1800d056a  xor     ecx, ecx; Expression
0x1800d056c  call    cs:__imp__invoke_watson
0x1800d0573  call    cs:__imp_free
0x1800d0579  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d0581  mov     [rsp+228h+Block], rdi
0x1800d0589  movdqu  [rsp+228h+var_138], xmm0
0x1800d0592  test    bl, 1
0x1800d0595  mov     ebx, 0Fh
0x1800d059a  jz      short loc_1800D05EB
0x1800d059c  mov     rax, qword ptr [rsp+228h+var_118+8]
0x1800d05a4  cmp     rax, rbx
0x1800d05a7  jbe     short loc_1800D05EB
0x1800d05a9  mov     rcx, [rsp+228h+var_128]; Block
0x1800d05b1  mov     rdx, rcx
0x1800d05b4  inc     rax
0x1800d05b7  cmp     rax, r14
0x1800d05ba  jb      short loc_1800D05E5
0x1800d05bc  mov     rcx, [rcx-8]
0x1800d05c0  sub     rdx, rcx
0x1800d05c3  lea     rax, [rdx-8]
0x1800d05c7  cmp     rax, 1Fh
0x1800d05cb  jbe     short loc_1800D05E5
0x1800d05cd  xor     eax, eax
0x1800d05cf  mov     [rsp+228h+Reserved], rax; Reserved
0x1800d05d4  xor     r9d, r9d; LineNo
0x1800d05d7  xor     r8d, r8d; FileName
0x1800d05da  xor     edx, edx; FunctionName
0x1800d05dc  xor     ecx, ecx; Expression
0x1800d05de  call    cs:__imp__invoke_watson
0x1800d05e5  call    cs:__imp_free
0x1800d05eb  xor     eax, eax
0x1800d05ed  mov     [rsp+228h+var_1B0], rax
0x1800d05f2  mov     rdi, [rsp+228h+var_1C0]
0x1800d05f7  mov     rax, [rdi]
0x1800d05fa  lea     r8, [rsp+228h+var_1B0]
0x1800d05ff  lea     rdx, IID_IRepoWriter
0x1800d0606  mov     rcx, rdi
0x1800d0609  mov     rax, [rax]
0x1800d060c  call    cs:__guard_dispatch_icall_fptr
0x1800d0612  mov     ecx, eax; this
0x1800d0614  lea     r8, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800d061b  mov     edx, 295h; int
0x1800d0620  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800d0625  xorps   xmm0, xmm0
0x1800d0628  movups  xmmword ptr [rsp+228h+Block], xmm0
0x1800d0630  xor     edx, edx
0x1800d0632  mov     qword ptr [rsp+228h+var_138], rdx
0x1800d063a  mov     qword ptr [rsp+228h+var_138+8], rbx
0x1800d0642  mov     byte ptr [rsp+228h+Block], dl
0x1800d0649  mov     r12, [rdi+20h]
0x1800d064d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800d0655  movdqu  [rsp+228h+var_118], xmm1
0x1800d065e  movups  xmm0, xmmword ptr [rsp+228h+Block]
0x1800d0666  movdqu  xmmword ptr [rsp+228h+var_128], xmm0
0x1800d066f  xorps   xmm0, xmm0
0x1800d0672  movups  xmmword ptr [rsp+228h+var_168], xmm0
  ... truncated ...
```
