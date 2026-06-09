# `RepoMan::DatFormat::InsertFile2(IRepoPackage *,wchar_t const *,IStream *,wchar_t const *,IRepoHash *,_REPOMAN_PATCH_TECH,_REPOMAN_FILE_TAGS,_REPOMAN_PATH_TAGS,IRepoFile * *)'::`3'::_lambda_1_::operator()(void)

- ea: `0x18007bdb4`
- end: `0x18007c6bf`
- name: `??R_lambda_1_@?2??InsertFile2@DatFormat@RepoMan@@UEAAJPEAUIRepoPackage@@PEB_WPEAUIStream@@1PEAUIRepoHash@@W4_REPOMAN_PATCH_TECH@@W4_REPOMAN_FILE_TAGS@@W4_REPOMAN_PATH_TAGS@@PEAPEAUIRepoFile@@@Z@QEAA@XZ`
- size: `2315`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180084590`

## callees

- `0x180013b14`
- `0x180016b9c`
- `0x18001c48c`
- `0x1800244bc`
- `0x18002854c`
- `0x18002e6b8`
- `0x18002f9b0`
- `0x18003386c`
- `0x18007bdb4`
- `0x18007ef14`
- `0x1800827e4`
- `0x180083744`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b028`
- `0x18018b0f0`
- `0x18018b208`
- `0x18018b9e4`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18007c5a9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18007c5a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c319`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c350`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c5bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c319`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c350`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007c5bf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18007c469`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18007c5a2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18007c469`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18007c5a2`
- `bcrypt!BCryptDestroyHash` at `0x18007bffb`
- `bcrypt!BCryptDestroyHash` at `0x18007c22d`
- `bcrypt!BCryptDestroyHash` at `0x18007bffb`
- `bcrypt!BCryptDestroyHash` at `0x18007c22d`

## string_xrefs

- `0x18007c638`: `src\repoman\src\inc\ComHelper.hpp`
- `0x18007c6a6`: `Attempting to write more than int64 bytes`
- `0x18007c658`: `unable to write requested bytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
unsigned __int8 *__fastcall `RepoMan::DatFormat::InsertFile2'::`3'::_lambda_1_::operator()(
        __int64 a1,
        unsigned __int8 *a2)
{
  unsigned int v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 *v8; // rax
  int v9; // r15d
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 *v12; // rdx
  __int64 v13; // rcx
  BCRYPT_HASH_HANDLE v14; // rcx
  unsigned __int8 *v15; // rsi
  __int64 v16; // r14
  __m128i si128; // xmm7
  __m128i v18; // xmm6
  __m128i v19; // xmm8
  unsigned int v20; // eax
  unsigned int v21; // r14d
  unsigned int v22; // eax
  const char *v23; // r9
  const unsigned __int8 *v24; // r14
  unsigned __int8 *v25; // rsi
  int v26; // r15d
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // eax
  const char *v30; // r9
  __int64 v31; // rsi
  unsigned __int8 *v32; // rdx
  signed __int64 v33; // r14
  __int64 v34; // rcx
  __int64 v35; // r8
  unsigned int v36; // eax
  const char *v37; // r9
  unsigned int v38; // eax
  const char *v39; // r9
  unsigned __int64 v40; // r14
  unsigned int v41; // eax
  const char *v42; // r9
  unsigned int v43; // eax
  const char *v44; // r9
  unsigned __int8 *v45; // r14
  unsigned __int8 *v46; // rsi
  int v47; // r15d
  __int64 v48; // rsi
  void *v49; // rcx
  void *v50; // rcx
  int v51; // eax
  unsigned int v52; // eax
  const char *v53; // r9
  __int64 v54; // rcx
  __int64 v55; // rcx
  _QWORD *v56; // rsi
  unsigned __int64 v57; // rax
  __int64 v58; // rcx
  unsigned __int64 v59; // r15
  unsigned __int8 *v60; // r14
  size_t v61; // rcx
  _QWORD *v62; // r15
  _QWORD *v63; // r15
  _QWORD *v64; // r14
  char *v65; // rcx
  __int64 v67; // [rsp+38h] [rbp-D0h] BYREF
  BCRYPT_HASH_HANDLE v68; // [rsp+40h] [rbp-C8h] BYREF
  __int64 Block; // [rsp+48h] [rbp-C0h] BYREF
  void *Block_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A8h]
  __int64 v72; // [rsp+68h] [rbp-A0h]
  __int64 v73; // [rsp+70h] [rbp-98h] BYREF
  __int64 v74; // [rsp+78h] [rbp-90h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int8 *v76; // [rsp+88h] [rbp-80h]
  unsigned __int8 *v77; // [rsp+90h] [rbp-78h]
  unsigned __int8 *v78; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int8 *v79; // [rsp+A0h] [rbp-68h]
  unsigned __int8 *v80; // [rsp+A8h] [rbp-60h]
  __int64 v81; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int8 *v82[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-40h]
  __int64 v84; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v85; // [rsp+E0h] [rbp-28h]
  __int128 v86; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v87; // [rsp+F8h] [rbp-10h]
  __int64 v88; // [rsp+108h] [rbp+0h]
  __int64 v89; // [rsp+110h] [rbp+8h]
  __int128 v90; // [rsp+118h] [rbp+10h] BYREF
  __m128i v91; // [rsp+128h] [rbp+20h]
  _QWORD v92[2]; // [rsp+138h] [rbp+30h] BYREF
  __m128i v93; // [rsp+148h] [rbp+40h]
  _QWORD v94[2]; // [rsp+158h] [rbp+50h] BYREF
  __m128i v95; // [rsp+168h] [rbp+60h]

  v77 = a2;
  LODWORD(v72) = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(
         *(_QWORD *)(a1 + 8),
         0,
         0,
         0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v4, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v5);
  if ( *(_BYTE *)a1 )
  {
    v7 = RepoMan::ComPtr<IStream>::Make<RepoMan::MemoryStream,>(&v68);
    LODWORD(v72) = 1;
    v8 = (__int64 *)RepoMan::ComPtr<IStream>::Make<RepoMan::DeflateStream,RepoMan::ComPtr<IStream>>(&Block, v7);
    v9 = 3;
    v10 = v74;
  }
  else
  {
    v10 = 0;
    v74 = 0;
    v8 = &v74;
    v9 = 4;
  }
  v11 = 0;
  v81 = 0;
  v12 = &v81;
  if ( &v81 != v8 )
  {
    v11 = *v8;
    v81 = *v8;
    *v8 = 0;
    v10 = v74;
  }
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    v13 = Block;
    if ( Block )
    {
      Block = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    v14 = v68;
    if ( v68 )
    {
      v68 = 0;
      (*(void (__fastcall **)(BCRYPT_HASH_HANDLE))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  *(_OWORD *)Block_8 = 0;
  v71 = 0;
  v15 = *(unsigned __int8 **)(a1 + 16);
  v76 = v15;
  v16 = 0;
  Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v15 )
  {
    v18 = _mm_load_si128((const __m128i *)&_xmm);
    v19 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v84 = 0;
      v85 = 0;
      v86 = 0;
      v87 = v19;
      LOBYTE(v86) = 0;
      v90 = 0;
      v91 = v19;
      LOBYTE(v90) = 0;
      v20 = dword_180212118;
      if ( (unsigned int)v15 < dword_180212118 )
        v20 = (unsigned int)v15;
      v21 = v20;
      v89 = v20;
      v88 = *(_QWORD *)(a1 + 16) - (_QWORD)v15;
      v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(
              *(_QWORD *)(a1 + 8),
              (unsigned int)v88,
              0,
              0);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v22, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v23);
      RepoMan::StreamBase<>::Read((__int64 *)v82, *(_QWORD *)(a1 + 8), v21);
      v24 = v82[0];
      v25 = v82[1];
      RepoMan::SHA256::SHA256((RepoMan::SHA256 *)&hHash);
      RepoMan::SHA256::HashData((RepoMan::SHA256 *)&hHash, v24, v25 - v24);
      RepoMan::SHA256::FinalizeAndGetHashValue(&hHash, &v78);
      v26 = v9 | 0x50;
      if ( hHash )
        BCryptDestroyHash(hHash);
      v9 = v26 | 0x20;
      v27 = RepoMan::Encoding::EncodeBase64(v92, &v78);
      if ( &v90 != (__int128 *)v27 )
      {
        v90 = *(_OWORD *)v27;
        v91 = *(__m128i *)(v27 + 16);
        *(_QWORD *)(v27 + 16) = 0;
        *(_QWORD *)(v27 + 24) = 15;
        *(_BYTE *)v27 = 0;
      }
      std::string::_Tidy_deallocate(v92);
      v92[0] = 19937;
      v93 = v18;
      std::vector<unsigned char>::_Tidy(&v78);
      if ( v11 )
      {
        v67 = 0;
        v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, 0, 1, &v67);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v29, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v30);
        v31 = v67;
        v84 = v67;
        v32 = v82[0];
        v77 = v82[0];
        v33 = v82[1] - v82[0];
        if ( (unsigned __int8 *)(v82[1] - v82[0]) > (unsigned __int8 *)0x7FFFFFFFFFFFFFFFLL )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            274,
            (unsigned int)"src\\repoman\\src\\inc\\StreamBase.hpp",
            (unsigned int)"Attempting to write more than int64 bytes",
            -1941503468,
            8);
        v34 = 0;
        while ( 1 )
        {
          v73 = v34;
          if ( v33 <= 0 )
            break;
          LODWORD(v67) = 0;
          v35 = (unsigned int)v33;
          if ( (unsigned __int64)v33 > 0xFFFFFFFF )
            v35 = 0xFFFFFFFFLL;
          v36 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, __int64 *))(*(_QWORD *)v11 + 32LL))(
                  v11,
                  &v32[v34],
                  v35,
                  &v67);
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v36, 282, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v37);
          if ( !(_DWORD)v67 )
            RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
              283,
              (unsigned int)"src\\repoman\\src\\inc\\StreamBase.hpp",
              (unsigned int)"unable to write requested bytes",
              -1941503468,
              8);
          v33 -= (unsigned int)v67;
          v34 = (unsigned int)v67 + v73;
          v32 = v77;
        }
        if ( v33 < 0 )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            288,
            (unsigned int)"src\\repoman\\src\\inc\\StreamBase.hpp",
            (unsigned int)"Wrote too many bytes to the stream",
            -1941503468,
            8);
        v73 = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, 0, 1, &v73);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v38, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v39);
        v40 = v73 - v31;
        v85 = v73 - v31;
        Block += v73 - v31;
        v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(
                v11,
                (unsigned int)v31,
                0,
                0);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v41, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v42);
        RepoMan::StreamBase<>::Read((__int64 *)&v78, v11, v40);
        v43 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(
                v11,
                (unsigned int)(v31 + v40),
                0,
                0);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v43, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v44);
        v45 = v78;
        v46 = v79;
        RepoMan::SHA256::SHA256((RepoMan::SHA256 *)&v68);
        RepoMan::SHA256::HashData((RepoMan::SHA256 *)&v68, v45, v46 - v45);
        RepoMan::SHA256::FinalizeAndGetHashValue(&v68, v92);
        v47 = v9 | 0x300;
        if ( v68 )
          BCryptDestroyHash(v68);
        v9 = v47 | 0x80;
        v48 = RepoMan::Encoding::EncodeBase64(v94, v92);
        if ( &v86 != (__int128 *)v48 )
        {
          std::string::_Tidy_deallocate(&v86);
          v86 = *(_OWORD *)v48;
          v87 = *(__m128i *)(v48 + 16);
          *(_QWORD *)(v48 + 16) = 0;
          *(_QWORD *)(v48 + 24) = 15;
          *(_BYTE *)v48 = 0;
        }
        std::string::_Tidy_deallocate(v94);
        v94[0] = 19937;
        v95 = v18;
        std::vector<unsigned char>::_Tidy(v92);
        std::vector<unsigned char>::_Tidy(&v78);
      }
      v15 = &v76[-v89];
      v76 -= v89;
      if ( Block_8[1] == (void *)v71 )
      {
        std::vector<RepoMan::DatFormat::Segment>::_Emplace_reallocate<RepoMan::DatFormat::Segment &>(
          Block_8,
          Block_8[1],
          &v84);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<RepoMan::DatFormat::Segment>>::construct<RepoMan::DatFormat::Segment,RepoMan::DatFormat::Segment &>(
          v28,
          Block_8[1],
          &v84);
        Block_8[1] = (char *)Block_8[1] + 96;
      }
      std::vector<unsigned char>::_Tidy(v82);
      *(__m128i *)v82 = si128;
      v83 = 19937;
      if ( v91.m128i_i64[1] > 0xFuLL )
      {
        v49 = (void *)v90;
        if ( (unsigned __int64)(v91.m128i_i64[1] + 1) >= 0x1000 )
        {
          v49 = *(void **)(v90 - 8);
          if ( (unsigned __int64)(v90 - (_QWORD)v49 - 8) > 0x1F )
LABEL_60:
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v49);
      }
      if ( v87.m128i_i64[1] > 0xFuLL )
      {
        v50 = (void *)v86;
        if ( (unsigned __int64)(v87.m128i_i64[1] + 1) >= 0x1000 )
        {
          v50 = *(void **)(v86 - 8);
          if ( (unsigned __int64)(v86 - (_QWORD)v50 - 8) > 0x1F )
            goto LABEL_60;
        }
        free(v50);
      }
    }
    while ( v15 );
    v16 = Block;
  }
  if ( v11 )
  {
    v67 = 0;
    LODWORD(v72) = v9 | 0x800;
    v51 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 24))(
            *(_QWORD *)(a1 + 24),
            &IID_IRepoFileInternal,
            &v67);
    if ( v51 < 0 )
      RepoMan::RaiseException<RepoMan::Exception,long>(
        208,
        "src\\repoman\\src\\inc\\ComHelper.hpp",
        "QueryInterface failed",
        (unsigned int)v51);
    v52 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 24LL))(v67, v16);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v52, 465, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v53);
    v54 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
  }
  v55 = *(_QWORD *)(a1 + 8);
  if ( v55 )
  {
    *(_QWORD *)(a1 + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  }
  v77 = a2;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v56 = Block_8[0];
  v57 = 0xAAAAAAAAAAAAAAABuLL * (((char *)Block_8[1] - (char *)Block_8[0]) >> 5);
  if ( v57 )
  {
    v58 = 0x2AAAAAAAAAAAAAALL;
    if ( v57 > 0x2AAAAAAAAAAAAAALL )
      std::vector<RepoMan::ComPtr<IRepoPatch>>::_Xlength(0x2AAAAAAAAAAAAAALL, v12, v6);
    v59 = 32 * (((char *)Block_8[1] - (char *)Block_8[0]) >> 5);
    if ( v59 )
    {
      v61 = 32 * (((char *)Block_8[1] - (char *)Block_8[0]) >> 5);
      if ( v59 < 0x1000 )
      {
        v60 = (unsigned __int8 *)malloc(v61);
        if ( !v60 )
          std::_Xbad_alloc();
      }
      else
      {
        v60 = (unsigned __int8 *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v61);
      }
      v56 = Block_8[0];
    }
    else
    {
      v60 = 0;
    }
    *(_QWORD *)a2 = v60;
    *((_QWORD *)a2 + 1) = v60;
    *((_QWORD *)a2 + 2) = &v60[v59];
    v76 = a2;
    v62 = Block_8[1];
    v78 = v60;
    v79 = v60;
    v80 = a2;
    if ( v56 != Block_8[1] )
    {
      do
      {
        std::_Default_allocator_traits<std::allocator<RepoMan::DatFormat::Segment>>::construct<RepoMan::DatFormat::Segment,RepoMan::DatFormat::Segment &>(
          v58,
          v60,
          v56);
        v60 += 96;
        v79 = v60;
        v56 += 12;
      }
      while ( v56 != v62 );
      v56 = Block_8[0];
    }
    *((_QWORD *)a2 + 1) = v60;
  }
  *((_QWORD *)a2 + 3) = v11;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v56 = Block_8[0];
  }
  if ( v56 )
  {
    v63 = Block_8[1];
    if ( v56 != Block_8[1] )
    {
      v64 = v56 + 8;
      do
      {
        std::string::_Tidy_deallocate(v64);
        *v64 = 19937;
        v64[2] = 0;
        v64[3] = 31;
        std::string::_Tidy_deallocate(v64 - 6);
        *(v64 - 6) = 19937;
        *(v64 - 4) = 0;
        *(v64 - 3) = 31;
        v64 += 12;
      }
      while ( v64 - 8 != v63 );
      v56 = Block_8[0];
    }
    v65 = (char *)v56;
    if ( (unsigned __int64)(32 * ((v71 - (__int64)v56) >> 5)) >= 0x1000 )
    {
      v56 = (_QWORD *)*(v56 - 1);
      if ( (unsigned __int64)(v65 - (char *)v56 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v56);
  }
  *(__m128i *)Block_8 = si128;
  v71 = 19937;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return a2;
}

```

## disassembly

```asm
0x18007bdb4  mov     rax, rsp
0x18007bdb7  mov     [rax+18h], rbx
0x18007bdbb  push    rbp
0x18007bdbc  push    rsi
0x18007bdbd  push    rdi
0x18007bdbe  push    r12
0x18007bdc0  push    r13
0x18007bdc2  push    r14
0x18007bdc4  push    r15
0x18007bdc6  lea     rbp, [rax-0E8h]
0x18007bdcd  sub     rsp, 1B0h
0x18007bdd4  movaps  xmmword ptr [rax-48h], xmm6
0x18007bdd8  movaps  xmmword ptr [rax-58h], xmm7
0x18007bddc  movaps  xmmword ptr [rax-68h], xmm8
0x18007bde1  mov     rax, cs:__security_cookie
0x18007bde8  xor     rax, rsp
0x18007bdeb  mov     [rbp+0E0h+var_70], rax
0x18007bdef  mov     r12, rdx
0x18007bdf2  mov     r13, rcx
0x18007bdf5  mov     [rbp+0E0h+var_158], rdx
0x18007bdf9  xor     ebx, ebx
0x18007bdfb  mov     dword ptr [rsp+1E0h+var_180], ebx
0x18007bdff  mov     rcx, [rcx+8]
0x18007be03  mov     rax, [rcx]
0x18007be06  xor     r9d, r9d
0x18007be09  xor     r8d, r8d
0x18007be0c  mov     edx, ebx
0x18007be0e  mov     rax, [rax+28h]
0x18007be12  call    cs:__guard_dispatch_icall_fptr
0x18007be18  mov     ecx, eax; this
0x18007be1a  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007be21  mov     edx, 169h; int
0x18007be26  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007be2b  cmp     [r13+0], bl
0x18007be2f  jz      short loc_18007BE5C
0x18007be31  lea     rcx, [rsp+1E0h+var_1A8]
0x18007be36  call    ??$Make@VMemoryStream@RepoMan@@$$V@?$ComPtr@UIStream@@@RepoMan@@SA?AV01@XZ; RepoMan::ComPtr<IStream>::Make<RepoMan::MemoryStream,>(void)
0x18007be3b  nop
0x18007be3c  mov     dword ptr [rsp+1E0h+var_180], 1
0x18007be44  mov     rdx, rax
0x18007be47  lea     rcx, [rsp+1E0h+Block]
0x18007be4c  call    ??$Make@VDeflateStream@RepoMan@@V?$ComPtr@UIStream@@@2@@?$ComPtr@UIStream@@@RepoMan@@SA?AV01@$$QEAV01@@Z; RepoMan::ComPtr<IStream>::Make<RepoMan::DeflateStream,RepoMan::ComPtr<IStream>>(RepoMan::ComPtr<IStream> &&)
0x18007be51  lea     r15d, [rbx+3]
0x18007be55  mov     rcx, [rsp+1E0h+var_170]
0x18007be5a  jmp     short loc_18007BE6F
0x18007be5c  mov     rcx, rbx
0x18007be5f  mov     [rsp+1E0h+var_170], rbx
0x18007be64  lea     rax, [rsp+1E0h+var_170]
0x18007be69  mov     r15d, 4
0x18007be6f  mov     rdi, rbx
0x18007be72  mov     [rbp+0E0h+var_138], rbx
0x18007be76  lea     rdx, [rbp+0E0h+var_138]
0x18007be7a  cmp     rdx, rax
0x18007be7d  jz      short loc_18007BE8E
0x18007be7f  mov     rdi, [rax]
0x18007be82  mov     [rbp+0E0h+var_138], rdi
0x18007be86  mov     [rax], rbx
0x18007be89  mov     rcx, [rsp+1E0h+var_170]
0x18007be8e  test    r15b, 4
0x18007be92  jz      short loc_18007BEAA
0x18007be94  and     r15d, 0FFFFFFFBh
0x18007be98  test    rcx, rcx
0x18007be9b  jz      short loc_18007BEAA
0x18007be9d  mov     rax, [rcx]
0x18007bea0  mov     rax, [rax+10h]
0x18007bea4  call    cs:__guard_dispatch_icall_fptr
0x18007beaa  test    r15b, 2
0x18007beae  jz      short loc_18007BED1
0x18007beb0  and     r15d, 0FFFFFFFDh
0x18007beb4  mov     rcx, [rsp+1E0h+Block]
0x18007beb9  test    rcx, rcx
0x18007bebc  jz      short loc_18007BED1
0x18007bebe  mov     [rsp+1E0h+Block], rbx
0x18007bec3  mov     rax, [rcx]
0x18007bec6  mov     rax, [rax+10h]
0x18007beca  call    cs:__guard_dispatch_icall_fptr
0x18007bed0  nop
0x18007bed1  test    r15b, 1
0x18007bed5  jz      short loc_18007BEF7
0x18007bed7  and     r15d, 0FFFFFFFEh
0x18007bedb  mov     rcx, [rsp+1E0h+var_1A8]
0x18007bee0  test    rcx, rcx
0x18007bee3  jz      short loc_18007BEF7
0x18007bee5  mov     [rsp+1E0h+var_1A8], rbx
0x18007beea  mov     rax, [rcx]
0x18007beed  mov     rax, [rax+10h]
0x18007bef1  call    cs:__guard_dispatch_icall_fptr
0x18007bef7  xorps   xmm0, xmm0
0x18007befa  movdqu  xmmword ptr [rsp+1E0h+Block+8], xmm0
0x18007bf00  mov     [rsp+1E0h+var_188], rbx
0x18007bf05  mov     rsi, [r13+10h]
0x18007bf09  mov     [rbp+0E0h+var_160], rsi
0x18007bf0d  mov     r14, rbx
0x18007bf10  mov     [rsp+1E0h+Block], rbx
0x18007bf15  movdqa  xmm7, cs:__xmm@0000000000004de10000000000004de1
0x18007bf1d  test    rsi, rsi
0x18007bf20  jz      loc_18007C364
0x18007bf26  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18007bf2e  movdqa  xmm8, cs:__xmm@000000000000000f0000000000000000
0x18007bf37  mov     [rbp+0E0h+var_110], rbx
0x18007bf3b  mov     [rbp+0E0h+var_108], rbx
0x18007bf3f  xorps   xmm0, xmm0
0x18007bf42  movups  [rbp+0E0h+var_100], xmm0
0x18007bf46  movdqa  [rbp+0E0h+var_F0], xmm8
0x18007bf4c  mov     byte ptr [rbp+0E0h+var_100], bl
0x18007bf4f  movups  [rbp+0E0h+var_D0], xmm0
0x18007bf53  movdqa  [rbp+0E0h+var_C0], xmm8
0x18007bf59  mov     byte ptr [rbp+0E0h+var_D0], bl
0x18007bf5c  mov     eax, cs:dword_180212118
0x18007bf62  cmp     esi, eax
0x18007bf64  cmovb   eax, esi
0x18007bf67  mov     r14d, eax
0x18007bf6a  mov     [rbp+0E0h+var_D8], r14
0x18007bf6e  mov     rax, [r13+10h]
0x18007bf72  sub     rax, rsi
0x18007bf75  mov     [rbp+0E0h+var_E0], rax
0x18007bf79  mov     edx, eax
0x18007bf7b  mov     rcx, [r13+8]
0x18007bf7f  mov     rax, [rcx]
0x18007bf82  xor     r9d, r9d
0x18007bf85  xor     r8d, r8d
0x18007bf88  mov     rax, [rax+28h]
0x18007bf8c  call    cs:__guard_dispatch_icall_fptr
0x18007bf92  mov     ecx, eax; this
0x18007bf94  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007bf9b  mov     edx, 169h; int
0x18007bfa0  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007bfa5  mov     r8d, r14d
0x18007bfa8  mov     rdx, [r13+8]
0x18007bfac  lea     rcx, [rbp+0E0h+var_130]
0x18007bfb0  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x18007bfb5  or      r15d, 10h
0x18007bfb9  mov     r14, [rbp+0E0h+var_130]
0x18007bfbd  mov     rsi, [rbp+0E0h+var_130+8]
0x18007bfc1  lea     rcx, [rsp+1E0h+hHash]; this
0x18007bfc6  call    ??0SHA256@RepoMan@@QEAA@XZ; RepoMan::SHA256::SHA256(void)
0x18007bfcb  nop
0x18007bfcc  sub     rsi, r14
0x18007bfcf  mov     r8, rsi; unsigned __int64
0x18007bfd2  mov     rdx, r14; unsigned __int8 *
0x18007bfd5  lea     rcx, [rsp+1E0h+hHash]; this
0x18007bfda  call    ?HashData@SHA256@RepoMan@@QEAAXPEBE_K@Z; RepoMan::SHA256::HashData(uchar const *,unsigned __int64)
0x18007bfdf  lea     rdx, [rbp+0E0h+var_150]
0x18007bfe3  lea     rcx, [rsp+1E0h+hHash]
0x18007bfe8  call    ?FinalizeAndGetHashValue@SHA256@RepoMan@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; RepoMan::SHA256::FinalizeAndGetHashValue(void)
0x18007bfed  or      r15d, 40h
0x18007bff1  mov     rcx, [rsp+1E0h+hHash]; hHash
0x18007bff6  test    rcx, rcx
0x18007bff9  jz      short loc_18007C001
0x18007bffb  call    cs:__imp_BCryptDestroyHash
0x18007c001  or      r15d, 20h
0x18007c005  lea     rdx, [rbp+0E0h+var_150]
0x18007c009  lea     rcx, [rbp+0E0h+var_B0]
0x18007c00d  call    ?EncodeBase64@Encoding@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; RepoMan::Encoding::EncodeBase64(std::vector<uchar> const &)
0x18007c012  lea     rcx, [rbp+0E0h+var_D0]
0x18007c016  cmp     rcx, rax
0x18007c019  jz      short loc_18007C038
0x18007c01b  movups  xmm0, xmmword ptr [rax]
0x18007c01e  movaps  [rbp+0E0h+var_D0], xmm0
0x18007c022  movups  xmm1, xmmword ptr [rax+10h]
0x18007c026  movaps  [rbp+0E0h+var_C0], xmm1
0x18007c02a  mov     [rax+10h], rbx
0x18007c02e  mov     qword ptr [rax+18h], 0Fh
0x18007c036  mov     [rax], bl
0x18007c038  lea     rcx, [rbp+0E0h+var_B0]
0x18007c03c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007c041  mov     r14d, 4DE1h
0x18007c047  mov     [rbp+0E0h+var_B0], r14
0x18007c04b  movdqu  [rbp+0E0h+var_A0], xmm6
0x18007c050  lea     rcx, [rbp+0E0h+var_150]
0x18007c054  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007c059  test    rdi, rdi
0x18007c05c  jz      loc_18007C2A2
0x18007c062  mov     [rsp+1E0h+var_1B0], rbx
0x18007c067  mov     rax, [rdi]
0x18007c06a  lea     r9, [rsp+1E0h+var_1B0]
0x18007c06f  mov     r8d, 1
0x18007c075  mov     rdx, rbx
0x18007c078  mov     rcx, rdi
0x18007c07b  mov     rax, [rax+28h]
0x18007c07f  call    cs:__guard_dispatch_icall_fptr
0x18007c085  mov     ecx, eax; this
0x18007c087  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007c08e  mov     edx, 161h; int
0x18007c093  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007c098  mov     rsi, [rsp+1E0h+var_1B0]
0x18007c09d  mov     [rbp+0E0h+var_110], rsi
0x18007c0a1  mov     r14, [rbp+0E0h+var_130+8]
0x18007c0a5  mov     rdx, [rbp+0E0h+var_130]
0x18007c0a9  mov     [rbp+0E0h+var_158], rdx
0x18007c0ad  sub     r14, rdx
0x18007c0b0  mov     rax, 7FFFFFFFFFFFFFFFh
0x18007c0ba  cmp     r14, rax
0x18007c0bd  ja      loc_18007C698
0x18007c0c3  mov     rcx, rbx
0x18007c0c6  jmp     short loc_18007C127
0x18007c0c8  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x18007c0cc  mov     rax, [rdi]
0x18007c0cf  mov     r8d, r14d
0x18007c0d2  mov     r9d, 0FFFFFFFFh
0x18007c0d8  cmp     r14, r9
0x18007c0db  cmova   r8d, r9d
0x18007c0df  add     rdx, rcx
0x18007c0e2  lea     r9, [rsp+1E0h+var_1B0]
0x18007c0e7  mov     rcx, rdi
0x18007c0ea  mov     rax, [rax+20h]
0x18007c0ee  call    cs:__guard_dispatch_icall_fptr
0x18007c0f4  mov     ecx, eax; this
0x18007c0f6  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007c0fd  mov     edx, 11Ah; int
0x18007c102  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007c107  mov     eax, dword ptr [rsp+1E0h+var_1B0]
0x18007c10b  test    eax, eax
0x18007c10d  jnz     short loc_18007C118
0x18007c10f  test    r14, r14
0x18007c112  jnz     loc_18007C64A
0x18007c118  sub     r14, rax
0x18007c11b  mov     rcx, [rsp+1E0h+var_178]
0x18007c120  add     rcx, rax
0x18007c123  mov     rdx, [rbp+0E0h+var_158]
0x18007c127  test    r14, r14
0x18007c12a  mov     [rsp+1E0h+var_178], rcx
0x18007c12f  jg      short loc_18007C0C8
0x18007c131  js      loc_18007C671
0x18007c137  mov     [rsp+1E0h+var_178], rbx
0x18007c13c  mov     rax, [rdi]
0x18007c13f  lea     r9, [rsp+1E0h+var_178]
0x18007c144  mov     r8d, 1
0x18007c14a  mov     rdx, rbx
0x18007c14d  mov     rcx, rdi
0x18007c150  mov     rax, [rax+28h]
0x18007c154  call    cs:__guard_dispatch_icall_fptr
0x18007c15a  mov     ecx, eax; this
0x18007c15c  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007c163  mov     edx, 161h; int
0x18007c168  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007c16d  mov     r14, [rsp+1E0h+var_178]
0x18007c172  sub     r14, rsi
0x18007c175  mov     [rbp+0E0h+var_108], r14
0x18007c179  add     [rsp+1E0h+Block], r14
0x18007c17e  mov     edx, esi
0x18007c180  mov     rax, [rdi]
0x18007c183  xor     r9d, r9d
0x18007c186  xor     r8d, r8d
0x18007c189  mov     rcx, rdi
0x18007c18c  mov     rax, [rax+28h]
0x18007c190  call    cs:__guard_dispatch_icall_fptr
0x18007c196  mov     ecx, eax; this
0x18007c198  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007c19f  mov     edx, 169h; int
0x18007c1a4  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007c1a9  mov     r8, r14
0x18007c1ac  mov     rdx, rdi
0x18007c1af  lea     rcx, [rbp+0E0h+var_150]
0x18007c1b3  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x18007c1b8  bts     r15d, 9
0x18007c1bd  lea     edx, [rsi+r14]
0x18007c1c1  mov     rax, [rdi]
0x18007c1c4  xor     r9d, r9d
0x18007c1c7  xor     r8d, r8d
0x18007c1ca  mov     rcx, rdi
0x18007c1cd  mov     rax, [rax+28h]
0x18007c1d1  call    cs:__guard_dispatch_icall_fptr
0x18007c1d7  mov     ecx, eax; this
0x18007c1d9  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18007c1e0  mov     edx, 169h; int
0x18007c1e5  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18007c1ea  mov     r14, [rbp+0E0h+var_150]
0x18007c1ee  mov     rsi, [rbp+0E0h+var_148]
0x18007c1f2  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18007c1f7  call    ??0SHA256@RepoMan@@QEAA@XZ; RepoMan::SHA256::SHA256(void)
0x18007c1fc  nop
0x18007c1fd  sub     rsi, r14
0x18007c200  mov     r8, rsi; unsigned __int64
0x18007c203  mov     rdx, r14; unsigned __int8 *
0x18007c206  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18007c20b  call    ?HashData@SHA256@RepoMan@@QEAAXPEBE_K@Z; RepoMan::SHA256::HashData(uchar const *,unsigned __int64)
0x18007c210  lea     rdx, [rbp+0E0h+var_B0]
0x18007c214  lea     rcx, [rsp+1E0h+var_1A8]
0x18007c219  call    ?FinalizeAndGetHashValue@SHA256@RepoMan@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; RepoMan::SHA256::FinalizeAndGetHashValue(void)
0x18007c21e  bts     r15d, 8
0x18007c223  mov     rcx, [rsp+1E0h+var_1A8]; hHash
0x18007c228  test    rcx, rcx
0x18007c22b  jz      short loc_18007C233
0x18007c22d  call    cs:__imp_BCryptDestroyHash
0x18007c233  bts     r15d, 7
0x18007c238  lea     rdx, [rbp+0E0h+var_B0]
0x18007c23c  lea     rcx, [rbp+0E0h+var_90]
0x18007c240  call    ?EncodeBase64@Encoding@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; RepoMan::Encoding::EncodeBase64(std::vector<uchar> const &)
0x18007c245  mov     rsi, rax
0x18007c248  lea     rax, [rbp+0E0h+var_100]
0x18007c24c  cmp     rax, rsi
0x18007c24f  jz      short loc_18007C277
0x18007c251  lea     rcx, [rbp+0E0h+var_100]
0x18007c255  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007c25a  movups  xmm0, xmmword ptr [rsi]
0x18007c25d  movaps  [rbp+0E0h+var_100], xmm0
0x18007c261  movups  xmm1, xmmword ptr [rsi+10h]
0x18007c265  movaps  [rbp+0E0h+var_F0], xmm1
0x18007c269  mov     [rsi+10h], rbx
  ... truncated ...
```
