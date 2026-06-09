# win_musl::consumption::ZipCentralConsumer::Extract(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 const &)

- ea: `0x18001d7d8`
- end: `0x18001ecb6`
- name: `?Extract@ZipCentralConsumer@consumption@win_musl@@QEAA?AU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@AEBU4@@Z`
- size: `5342`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d6c0`

## callees

- `0x18001d000`
- `0x18001d7d8`
- `0x18001edc4`
- `0x18001f158`
- `0x18001f9f8`
- `0x18001faac`
- `0x18001fd48`
- `0x180021d74`
- `0x180022fe4`
- `0x180023048`
- `0x18002db70`
- `0x18006aecc`
- `0x18006dda8`
- `0x18006f960`
- `0x18008e438`
- `0x18008e6dc`
- `0x18008e708`
- `0x180097a84`
- `0x1800b6f0c`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d975`
- `msvcrt!memmove_s` at `0x18001da8a`
- `msvcrt!memmove_s` at `0x18001db4f`
- `msvcrt!memmove_s` at `0x18001dbd8`
- `msvcrt!memmove_s` at `0x18001dc6a`
- `msvcrt!memmove_s` at `0x18001dcde`
- `msvcrt!memmove_s` at `0x18001dd75`
- `msvcrt!memmove_s` at `0x18001d975`
- `msvcrt!memmove_s` at `0x18001da8a`
- `msvcrt!memmove_s` at `0x18001db4f`
- `msvcrt!memmove_s` at `0x18001dbd8`
- `msvcrt!memmove_s` at `0x18001dc6a`
- `msvcrt!memmove_s` at `0x18001dcde`
- `msvcrt!memmove_s` at `0x18001dd75`

## string_xrefs

- `0x18001e42c`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18001e46b`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18001eb1d`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18001e420`: `win_musl::consumption::readExtras`
- `0x18001e45f`: `win_musl::consumption::readExtras`
- `0x18001eb16`: `win_musl::consumption::readExtras`
- `0x18001e67f`: `win_musl::detail::vector_read`
- `0x18001e72c`: `win_musl::detail::vector_read`
- `0x18001e7c7`: `win_musl::detail::vector_read`
- `0x18001e862`: `win_musl::detail::vector_read`
- `0x18001e8fd`: `win_musl::detail::vector_read`
- `0x18001e982`: `win_musl::detail::vector_read`
- `0x18001ea16`: `win_musl::detail::vector_read`
- `0x18001e78b`: `currentEntryByteSizeComment`
- `0x18001ea53`: `central directory entry too big. Total size must not be more than 65,535.`
- `0x18001ec6c`: `Unexpected bytes remaining during extraction.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__m128i *__fastcall win_musl::consumption::ZipCentralConsumer::Extract(__int64 a1, __m128i *a2, char **a3)
{
  __int64 v5; // rcx
  _BYTE *v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // r9
  __int64 v9; // r10
  __m128i v10; // xmm6
  _BYTE **v11; // rdi
  _BYTE *v12; // rax
  _BYTE *v13; // rcx
  _BYTE *v14; // rdx
  unsigned int v15; // edx
  __int64 v16; // r9
  __int64 v17; // r11
  unsigned __int16 v18; // r8
  unsigned __int16 v19; // r10
  char v20; // cl
  __m128i *v21; // rdi
  __int64 v22; // rsi
  __int32 v23; // eax
  char *v24; // rbx
  char *v25; // rcx
  char *v26; // rdx
  __int64 v27; // rsi
  unsigned int v28; // edi
  unsigned int v29; // r14d
  char v30; // al
  unsigned int v31; // ecx
  __m128i *v32; // rbx
  __int64 v33; // rsi
  __int32 v34; // eax
  char *v35; // rdi
  char *v36; // rcx
  char *v37; // rdx
  __m128i v38; // xmm0
  __int64 v39; // rsi
  __int32 v40; // eax
  char *v41; // rdi
  char *v42; // rcx
  char *v43; // rdx
  __int64 v44; // rsi
  __int32 v45; // eax
  char *v46; // rdi
  char *v47; // rcx
  char *v48; // rdx
  __int64 v49; // rsi
  __int32 v50; // eax
  char *v51; // rdi
  char *v52; // rcx
  char *v53; // rdx
  __int64 v54; // rsi
  __int32 v55; // eax
  char *v56; // rdi
  char *v57; // rcx
  char *v58; // rdx
  __int64 v59; // rsi
  __int32 v60; // eax
  char *v61; // rdi
  char *v62; // rcx
  char *v63; // rdx
  unsigned int v64; // edx
  char v65; // al
  unsigned int v66; // r12d
  __m128i *v67; // r13
  unsigned __int64 v68; // rdi
  unsigned __int64 v69; // rbx
  _QWORD *v70; // rsi
  char *v71; // r14
  _QWORD *v72; // rcx
  unsigned __int64 v73; // rcx
  char v74; // al
  unsigned int v75; // r13d
  __m128i *v76; // rbx
  char *v77; // r14
  char *v78; // rsi
  unsigned int v79; // ecx
  _BYTE *v80; // rcx
  unsigned int i; // eax
  char *v82; // rcx
  char v83; // al
  __m128i *v84; // r13
  unsigned __int64 v85; // r12
  unsigned __int64 v86; // rdi
  void **v87; // rcx
  char *v88; // rsi
  void **v89; // rbx
  void **v90; // rax
  unsigned __int64 v91; // rcx
  __int64 v92; // rax
  __m128i *v93; // rbx
  __int16 Then; // bx
  __int64 v96; // r12
  unsigned __int64 v97; // rdi
  unsigned __int64 v98; // rax
  __int64 v99; // rax
  unsigned __int64 v100; // rax
  __int64 v101; // r8
  __int64 v102; // r9
  unsigned __int64 v103; // rdx
  __int64 v104; // rbx
  __int64 v105; // rbx
  __m128i v106; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v107; // [rsp+58h] [rbp-B0h] BYREF
  int Destination; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v109; // [rsp+60h] [rbp-A8h] BYREF
  __m128i *v110; // [rsp+68h] [rbp-A0h] BYREF
  int v111; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 v112; // [rsp+74h] [rbp-94h] BYREF
  __m128i v113; // [rsp+78h] [rbp-90h] BYREF
  __m128i v114; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v115; // [rsp+98h] [rbp-70h]
  __m128i v116; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v117; // [rsp+B8h] [rbp-50h] BYREF
  __m128i *v118; // [rsp+C8h] [rbp-40h]
  __int64 v119; // [rsp+D0h] [rbp-38h]
  __int16 v120; // [rsp+D8h] [rbp-30h] BYREF
  int v121; // [rsp+DAh] [rbp-2Eh]
  __int16 v122; // [rsp+DEh] [rbp-2Ah]
  void *v123; // [rsp+E0h] [rbp-28h]
  __int64 v124; // [rsp+E8h] [rbp-20h]
  __int64 v125; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v126; // [rsp+F8h] [rbp-10h]
  void **v127; // [rsp+108h] [rbp+0h] BYREF
  char v128; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v129[2]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v130; // [rsp+128h] [rbp+20h]
  unsigned __int64 v131; // [rsp+130h] [rbp+28h]
  char v132[8]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE *v133; // [rsp+148h] [rbp+40h]
  _BYTE *v134; // [rsp+150h] [rbp+48h]
  _BYTE v135[16]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v136; // [rsp+170h] [rbp+68h]
  int v137; // [rsp+188h] [rbp+80h]
  unsigned int v138; // [rsp+18Ch] [rbp+84h]
  __int64 v139; // [rsp+1C0h] [rbp+B8h]
  char v140; // [rsp+1D5h] [rbp+CDh]
  char v141; // [rsp+1D8h] [rbp+D0h] BYREF
  void *Block[2]; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v143; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v144; // [rsp+1F8h] [rbp+F0h]
  _BYTE pExceptionObject[160]; // [rsp+208h] [rbp+100h] BYREF

  v119 = -2;
  v118 = a2;
  v5 = a1 + 80;
  v6 = *(_BYTE **)(v5 + 8);
  if ( v6 )
    v7 = *(_QWORD *)(v5 + 16) - (_QWORD)v6;
  else
    v7 = 0;
  v8 = *(unsigned int *)(a1 + 112);
  v9 = *(unsigned int *)a3;
  if ( v9 + v7 < v8 )
  {
    std::vector<unsigned char>::_Insert<unsigned char const *>(v5, *(_BYTE **)(a1 + 96), a3[1], (__int64)&a3[1][v9]);
    a2->m128i_i64[0] = 0;
    a2->m128i_i64[1] = 0;
    return a2;
  }
  v10 = *(__m128i *)a3;
  v116 = *(__m128i *)a3;
  v11 = (_BYTE **)(a1 + 96);
  v115 = (_QWORD *)(a1 + 96);
  if ( v6 )
  {
    v12 = (_BYTE *)(*v11 - v6);
    if ( *v11 != v6 )
    {
      if ( (unsigned __int64)v12 < v8 )
      {
        v105 = v116.m128i_i64[1] + (unsigned int)(v8 - (_DWORD)v12);
        std::vector<unsigned char>::_Insert<unsigned char const *>(v5, *v11, (char *)v116.m128i_i64[1], v105);
        v10 = *(__m128i *)win_musl::detail::get_vector_tail_private(
                            &v117,
                            &v116,
                            v105,
                            "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
                            336,
                            "win_musl::consumption::ZipCentralConsumer::Extract",
                            L"new_begin is out-of-range: vector expression (earlyReturnVector), new_begin expression (bytesEnd)");
      }
      v115 = (_QWORD *)(a1 + 96);
    }
  }
  v114 = v10;
  v13 = *(_BYTE **)(a1 + 88);
  if ( v13 )
    v14 = (_BYTE *)(*v11 - v13);
  else
    LODWORD(v14) = 0;
  v106 = (__m128i)(unsigned int)v14;
  if ( v13 && *v11 != v13 )
    v106.m128i_i64[1] = (__int64)v13;
  v113 = v106;
  win_musl::ZipFileLocal::ZipFileLocal((win_musl::ZipFileLocal *)&v127);
  v127 = &win_musl::ZipFileCentral::`vftable';
  v144 = 15;
  v143 = 0;
  LOBYTE(Block[0]) = 0;
  v18 = 0;
  v111 = 0;
  LOWORD(v109) = 0;
  v19 = 0;
  LODWORD(v110) = 0;
  v112 = 0;
  if ( v15 && v16 )
  {
    v20 = 0;
  }
  else
  {
    v20 = 1;
    v15 = _mm_cvtsi128_si32(v10);
  }
  v21 = &v113;
  if ( v20 )
    v21 = &v114;
  if ( v15 < 4 || !*(_BYTE *)(a1 + 116) )
  {
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
LABEL_173:
    v29 = v114.m128i_i32[0];
    goto LABEL_33;
  }
  v22 = v21->m128i_u32[0];
  v23 = v21->m128i_i32[1];
  v24 = (char *)v21->m128i_i64[1];
  if ( (unsigned int)v22 < 4 )
  {
    v106.m128i_i32[0] = v21->m128i_i32[0];
    v106.m128i_i32[1] = v23;
    v106.m128i_i64[1] = (__int64)v24;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      357,
      v17,
      "signatureCheck",
      4,
      &v106);
  }
  Destination = 0;
  memmove_s(&Destination, 4u, v24, 4u);
  if ( !v24 || (v25 = v24 + 4, v26 = &v24[v22], &v24[v22] == v24 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v24 > v25 || v25 > v26 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v26 - (_DWORD)v25);
    v106.m128i_i64[1] = (__int64)(v24 + 4);
  }
  *v21 = v106;
  LOWORD(v107) = 255;
  if ( Destination != 33639248 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 8) + 40LL))(a1 + 8, *(_QWORD *)(a1 + 32));
    win_dox::ByteSender::StopSend((win_dox::ByteSender *)(a1 + 64));
    a2->m128i_i64[0] = 0;
    a2->m128i_i64[1] = 0;
LABEL_196:
    win_musl::ZipFileCentral::~ZipFileCentral((win_musl::ZipFileCentral *)&v127);
    return a2;
  }
  *(_DWORD *)(a1 + 112) = 46;
  v27 = v113.m128i_i64[1];
  v28 = v113.m128i_i32[0];
  if ( v113.m128i_i32[0] )
  {
    if ( v113.m128i_i64[1] && v113.m128i_i32[0] < 0x2Au )
      goto LABEL_217;
    if ( v113.m128i_i64[1] )
    {
      v18 = v111;
      v19 = (unsigned __int16)v110;
      goto LABEL_173;
    }
  }
  v29 = v114.m128i_i32[0];
  if ( v114.m128i_i32[0] < 0x2Au )
    goto LABEL_217;
  v18 = v111;
  v19 = (unsigned __int16)v110;
LABEL_33:
  v107 = 0;
  v111 = 0;
  if ( v28 && v27 )
  {
    v30 = 0;
    v31 = v28;
  }
  else
  {
    v30 = 1;
    v31 = v29;
  }
  v32 = &v113;
  if ( v30 )
    v32 = &v114;
  if ( v31 < 0x2A )
    goto LABEL_83;
  v33 = v32->m128i_u32[0];
  v34 = v32->m128i_i32[1];
  v35 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v33 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v34;
    v106.m128i_i64[1] = (__int64)v35;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      413,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "versionMadeBy",
      2,
      &v106);
  }
  LOWORD(Destination) = 0;
  memmove_s(&Destination, 2u, v35, 2u);
  if ( !v35 || (v36 = v35 + 2, v37 = &v35[v33], &v35[v33] == v35 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v35 > v36 || v36 > v37 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v37 - (_DWORD)v36);
    v106.m128i_i64[1] = (__int64)(v35 + 2);
  }
  v38 = v106;
  *v32 = v106;
  LOWORD(v107) = 255;
  v140 = Destination;
  v137 = BYTE1(Destination);
  v116 = v38;
  win_musl::consumption::readFileHeaderCommon((__int64)&v127, (unsigned int *)&v116, v32, &v109, &v112);
  v39 = v32->m128i_u32[0];
  v40 = v32->m128i_i32[1];
  v41 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v39 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v40;
    v106.m128i_i64[1] = (__int64)v41;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      427,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "currentEntryByteSizeComment",
      2,
      &v106);
  }
  LOWORD(Destination) = 0;
  memmove_s(&Destination, 2u, v41, 2u);
  if ( !v41 || (v42 = v41 + 2, v43 = &v41[v39], &v41[v39] == v41 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v41 > v42 || v42 > v43 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v43 - (_DWORD)v42);
    v106.m128i_i64[1] = (__int64)(v41 + 2);
  }
  *v32 = v106;
  LOWORD(v107) = 255;
  v44 = v32->m128i_u32[0];
  v45 = v32->m128i_i32[1];
  v46 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v44 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v45;
    v106.m128i_i64[1] = (__int64)v46;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      430,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "diskStartNumber",
      2,
      &v106);
  }
  LOWORD(v107) = 0;
  memmove_s(&v107, 2u, v46, 2u);
  if ( !v46 || (v47 = v46 + 2, v48 = &v46[v44], &v46[v44] == v46 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v46 > v47 || v47 > v48 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v48 - (_DWORD)v47);
    v106.m128i_i64[1] = (__int64)(v46 + 2);
  }
  *v32 = v106;
  LOWORD(v110) = 255;
  v111 = (unsigned __int16)v107;
  v49 = v32->m128i_u32[0];
  v50 = v32->m128i_i32[1];
  v51 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v49 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v50;
    v106.m128i_i64[1] = (__int64)v51;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      434,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "internalAttributes",
      2,
      &v106);
  }
  LOWORD(v110) = 0;
  memmove_s(&v110, 2u, v51, 2u);
  if ( !v51 || (v52 = v51 + 2, v53 = &v51[v49], &v51[v49] == v51 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v51 > v52 || v52 > v53 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v53 - (_DWORD)v52);
    v106.m128i_i64[1] = (__int64)(v51 + 2);
  }
  *v32 = v106;
  v54 = v32->m128i_u32[0];
  v55 = v32->m128i_i32[1];
  v56 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v54 < 4 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v55;
    v106.m128i_i64[1] = (__int64)v56;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      437,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "entry.header.attributes",
      4,
      &v106);
  }
  v107 = 0;
  memmove_s(&v107, 4u, v56, 4u);
  if ( !v56 || (v57 = v56 + 4, v58 = &v56[v54], &v56[v54] == v56 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v56 > v57 || v57 > v58 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v58 - (_DWORD)v57);
    v106.m128i_i64[1] = (__int64)(v56 + 4);
  }
  *v32 = v106;
  LOWORD(v110) = 255;
  v138 = v107;
  v59 = v32->m128i_u32[0];
  v60 = v32->m128i_i32[1];
  v61 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v59 < 4 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v60;
    v106.m128i_i64[1] = (__int64)v61;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      440,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "entry.header.header_offset",
      4,
      &v106);
  }
  v107 = 0;
  memmove_s(&v107, 4u, v61, 4u);
  if ( !v61 || (v62 = v61 + 4, v63 = &v61[v59], &v61[v59] == v61 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v61 > v62 || v62 > v63 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v63 - (_DWORD)v62);
    v106.m128i_i64[1] = (__int64)(v61 + 4);
  }
  *v32 = v106;
  v139 = v107;
  v19 = v112;
  LODWORD(v110) = v112;
  v18 = v109;
  v64 = (unsigned __int16)v109 + v112 + (unsigned __int16)Destination;
  if ( v64 + 46 > 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1C4u,
      0x80511009,
      (struct win_musl::TStringEllipseBase *)L"central directory entry too big. Total size must not be more than 65,535.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 112) = v64 + 42;
  if ( *(_BYTE *)(a1 + 116) )
    *(_DWORD *)(a1 + 112) = v64 + 46;
  v27 = v113.m128i_i64[1];
  v28 = v113.m128i_i32[0];
  if ( v113.m128i_i32[0] && v113.m128i_i64[1] && v113.m128i_i32[0] < v64 )
    goto LABEL_217;
  v107 = (unsigned __int16)Destination;
  if ( !v113.m128i_i32[0] || !v113.m128i_i64[1] )
  {
    v29 = v114.m128i_i32[0];
    if ( v114.m128i_i32[0] >= v64 )
      goto LABEL_83;
LABEL_217:
    *a2 = v10;
    goto LABEL_196;
  }
  v29 = v114.m128i_i32[0];
LABEL_83:
  if ( v28 && v27 )
  {
    v65 = 0;
    v66 = v28;
  }
  else
  {
    v65 = 1;
    v66 = v29;
  }
  v67 = &v113;
  if ( v65 )
    v67 = &v114;
  if ( v66 >= v18 )
  {
    v68 = v67->m128i_u64[1];
    v69 = v68 + v18;
    if ( v131 < 0x10 )
    {
      v70 = v129;
      v71 = (char *)v129 + v130;
    }
    else
    {
      v70 = (_QWORD *)v129[0];
      v71 = (char *)(v129[0] + v130);
    }
    v126 = 15;
    v125 = 0;
    LOBYTE(v123) = 0;
    std::string::_Construct<unsigned char const *>(&v120, v68, v68 + v18);
    v72 = v129;
    if ( v131 >= 0x10 )
      LODWORD(v72) = v129[0];
    std::string::replace(
      (unsigned int)&v128,
      v70 != 0 ? (_DWORD)v70 - (_DWORD)v72 : 0,
      v71 != 0 ? (_DWORD)v71 - (_DWORD)v70 : 0,
      (unsigned int)&v120,
      0,
      -1);
    if ( v126 >= 0x10 )
      operator delete(v123);
    if ( v66 && v68 && (v73 = v68 + v66, v73 != v69) )
    {
      if ( v68 > v69 || v69 > v73 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x1FCu,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)(v73 - v69);
      v106.m128i_i64[1] = v69;
    }
    else
    {
      v106 = 0u;
    }
    *v67 = v106;
    v29 = v114.m128i_i32[0];
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
    v19 = (unsigned __int16)v110;
  }
  if ( v28 && v27 )
  {
    v74 = 0;
    v75 = v28;
  }
  else
  {
    v74 = 1;
    v75 = v29;
  }
  v76 = &v113;
  if ( v74 )
    v76 = &v114;
  v110 = v76;
  if ( v75 >= v19 )
  {
    v77 = (char *)v76->m128i_i64[1];
    v78 = &v77[v19];
    if ( v133 != v134 )
      v134 = v133;
    std::vector<unsigned char>::_Insert<unsigned char const *>((__int64)v132, v133, v77, (__int64)&v77[v19]);
    if ( v133 )
      v79 = (_DWORD)v134 - (_DWORD)v133;
    else
      v79 = 0;
    v106 = (__m128i)v79;
    v80 = 0;
    if ( v133 && v134 != v133 )
    {
      v106.m128i_i64[1] = (__int64)v133;
      v80 = v133;
    }
    for ( i = v106.m128i_i32[0]; ; v106.m128i_i64[0] = i )
    {
      v106.m128i_i64[1] = (__int64)v80;
      if ( !i || !v80 )
        break;
      v117 = v106;
      Then = win_musl::detail::readThenLog<unsigned short>(
               (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
               65,
               (unsigned int)"win_musl::consumption::readExtras",
               (unsigned int)"type",
               (__int64)&v117,
               (__int64)&v106);
      v117 = v106;
      LOWORD(v109) = win_musl::detail::readThenLog<unsigned short>(
                       (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
                       69,
                       (unsigned int)"win_musl::consumption::readExtras",
                       (unsigned int)"size",
                       (__int64)&v117,
                       (__int64)&v106);
      v96 = v106.m128i_u32[0];
      if ( (unsigned int)(unsigned __int16)v109 > v106.m128i_i32[0] )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x4Cu,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v121 = 0;
      v122 = 0;
      v120 = Then;
      HIDWORD(v123) = v106.m128i_i32[1];
      v97 = v106.m128i_u64[1];
      v124 = v106.m128i_i64[1];
      LODWORD(v123) = (unsigned __int16)v109;
      if ( Then == 1 )
      {
        v116.m128i_i32[0] = (unsigned __int16)v109;
        v116.m128i_i32[1] = v106.m128i_i32[1];
        v116.m128i_i64[1] = v106.m128i_i64[1];
        win_musl::consumption::readZip64Extra(&v127, &v116, &v111);
      }
      else
      {
        v99 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(v135);
        v100 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(v135, v99);
        if ( v103 >= v100 )
        {
          std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(v135, v136, v101, &v120);
        }
        else
        {
          v104 = v136;
          std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
            v136,
            v102,
            &v120);
          v136 = v104 + 24;
        }
      }
      if ( (_DWORD)v96
        && v97
        && (v80 = (_BYTE *)(v97 + (unsigned __int16)v109), v98 = v97 + v96, (_BYTE *)(v97 + v96) != v80) )
      {
        if ( v97 > (unsigned __int64)v80 || (unsigned __int64)v80 > v98 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0x65u,
            0x80070057,
            (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (extraCursor), new_begin"
                                                    " expression (dd::vector_begin(extraCursor) + size)");
          throw (SplException::THResultException *)pExceptionObject;
        }
        i = v98 - (_DWORD)v80;
      }
      else
      {
        v80 = 0;
        i = 0;
      }
    }
    if ( v75 && v77 && (v82 = &v77[v75], v82 != v78) )
    {
      if ( v77 > v78 || v78 > v82 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x218u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)((_DWORD)v82 - (_DWORD)v78);
      v106.m128i_i64[1] = (__int64)v78;
    }
    else
    {
      v106 = 0u;
    }
    *v110 = v106;
    v29 = v114.m128i_i32[0];
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
  }
  if ( v111 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x224u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Disk number start must be 0 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v28 && v27 )
  {
    v83 = 0;
    v29 = v28;
  }
  else
  {
    v83 = 1;
  }
  v84 = &v113;
  if ( v83 )
    v84 = &v114;
  if ( v29 >= (unsigned __int16)v107 )
  {
    v85 = v84->m128i_u64[1];
    v86 = v85 + (unsigned __int16)v107;
    v87 = Block;
    if ( v144 >= 0x10 )
      v87 = (void **)Block[0];
    v88 = (char *)v87 + v143;
    v89 = Block;
    if ( v144 >= 0x10 )
      v89 = (void **)Block[0];
    v126 = 15;
    v125 = 0;
    LOBYTE(v123) = 0;
    std::string::_Construct<unsigned char const *>(&v120, v85, v86);
    if ( v88 )
      LODWORD(v88) = (_DWORD)v88 - (_DWORD)v89;
    v90 = Block;
    if ( v144 >= 0x10 )
      LODWORD(v90) = Block[0];
    if ( v89 )
      LODWORD(v89) = (_DWORD)v89 - (_DWORD)v90;
    std::string::replace((unsigned int)&v141, (_DWORD)v89, (_DWORD)v88, (unsigned int)&v120, 0, -1);
    if ( v126 >= 0x10 )
      operator delete(v123);
    if ( v29 && v85 && (v91 = v85 + v29, v91 != v86) )
    {
      if ( v85 > v86 || v86 > v91 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x238u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)(v91 - v86);
      v106.m128i_i64[1] = v86;
    }
    else
    {
      v106 = 0u;
    }
    *v84 = v106;
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
  }
  *(_QWORD *)(a1 + 32) += *(unsigned int *)(a1 + 112);
  win_musl::consumption::ZipCentralConsumer::AddFile(
    (win_musl::consumption::ZipCentralConsumer *)a1,
    (const struct win_musl::ZipFileCentral *)&v127);
  *(_DWORD *)(a1 + 112) = 4;
  *(_BYTE *)(a1 + 116) = 1;
  if ( v28 && v27 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x24Bu,
      0x80511001,
      (struct win_musl::TStringEllipseBase *)L"Unexpected bytes remaining during extraction.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v92 = *(_QWORD *)(a1 + 88);
  if ( v92 != *v115 )
    *v115 = v92;
  v93 = v118;
  *v118 = v114;
  v127 = &win_musl::ZipFileCentral::`vftable';
  if ( v144 >= 0x10 )
    operator delete(Block[0]);
  v144 = 15;
  v143 = 0;
  LOBYTE(Block[0]) = 0;
  win_musl::ZipFileLocal::~ZipFileLocal((win_musl::ZipFileLocal *)&v127);
  return v93;
}

```

## disassembly

```asm
0x18001d7d8  mov     rax, rsp
0x18001d7db  push    rbp
0x18001d7dc  push    rsi
0x18001d7dd  push    rdi
0x18001d7de  push    r12
0x18001d7e0  push    r13
0x18001d7e2  push    r14
0x18001d7e4  push    r15
0x18001d7e6  lea     rbp, [rax-1F8h]
0x18001d7ed  sub     rsp, 2C0h
0x18001d7f4  mov     [rbp+1F0h+var_228], 0FFFFFFFFFFFFFFFEh
0x18001d7fc  mov     [rax+20h], rbx
0x18001d800  movaps  xmmword ptr [rax-48h], xmm6
0x18001d804  mov     rax, cs:__security_cookie
0x18001d80b  xor     rax, rsp
0x18001d80e  mov     [rbp+1F0h+var_50], rax
0x18001d815  mov     r12, rdx
0x18001d818  mov     [rbp+1F0h+var_230], rdx
0x18001d81c  mov     r15, rcx
0x18001d81f  add     rcx, 50h ; 'P'
0x18001d823  mov     rdx, [rcx+8]
0x18001d827  xor     r13d, r13d
0x18001d82a  test    rdx, rdx
0x18001d82d  jz      loc_18001E2FD
0x18001d833  mov     rax, [rcx+10h]
0x18001d837  sub     rax, rdx
0x18001d83a  mov     r9d, [r15+70h]
0x18001d83e  mov     r10d, [r8]
0x18001d841  add     rax, r10
0x18001d844  cmp     rax, r9
0x18001d847  jb      loc_18001E57B
0x18001d84d  movups  xmm6, xmmword ptr [r8]
0x18001d851  movaps  [rbp+1F0h+var_250], xmm6
0x18001d855  lea     r11, aWinMuslConsump_2; "win_musl::consumption::ZipCentralConsum"...
0x18001d85c  lea     rdi, [r15+60h]
0x18001d860  mov     [rbp+1F0h+var_260], rdi
0x18001d864  test    rdx, rdx
0x18001d867  jz      short loc_18001D87E
0x18001d869  mov     rax, [rdi]
0x18001d86c  sub     rax, rdx
0x18001d86f  jz      short loc_18001D87E
0x18001d871  cmp     rax, r9
0x18001d874  jb      loc_18001E5CE
0x18001d87a  mov     [rbp+1F0h+var_260], rdi
0x18001d87e  movdqa  [rbp+1F0h+var_270], xmm6
0x18001d883  mov     rcx, [r15+58h]
0x18001d887  test    rcx, rcx
0x18001d88a  jz      loc_18001E305
0x18001d890  mov     rdx, [rdi]
0x18001d893  sub     rdx, rcx
0x18001d896  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001d89a  xor     eax, eax
0x18001d89c  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001d8a0  mov     qword ptr [rsp+2F0h+var_2A8], r13
0x18001d8a5  mov     r9, r13
0x18001d8a8  test    rcx, rcx
0x18001d8ab  jz      short loc_18001D8BA
0x18001d8ad  cmp     [rdi], rcx
0x18001d8b0  jz      short loc_18001D8BA
0x18001d8b2  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001d8b7  mov     r9, rcx
0x18001d8ba  movaps  xmm0, [rsp+2F0h+var_2B8+8]
0x18001d8bf  movdqa  [rsp+2F0h+var_288+8], xmm0
0x18001d8c5  lea     rcx, [rbp+1F0h+var_1F0]; this
0x18001d8c9  call    ??0ZipFileLocal@win_musl@@QEAA@XZ; win_musl::ZipFileLocal::ZipFileLocal(void)
0x18001d8ce  lea     rax, ??_7ZipFileCentral@win_musl@@6B@; const win_musl::ZipFileCentral::`vftable'
0x18001d8d5  mov     [rbp+1F0h+var_1F0], rax
0x18001d8d9  mov     [rbp+1F0h+var_100], 0Fh
0x18001d8e4  mov     [rbp+1F0h+var_108], r13
0x18001d8eb  mov     byte ptr [rbp+1F0h+Block], r13b
0x18001d8f2  mov     r8d, r13d
0x18001d8f5  mov     dword ptr [rsp+2F0h+var_288], r13d
0x18001d8fa  mov     word ptr [rsp+2F0h+var_298], r13w
0x18001d900  mov     r10d, r13d
0x18001d903  mov     dword ptr [rsp+2F0h+var_290], r13d
0x18001d908  mov     word ptr [rsp+2F0h+var_288+4], r13w
0x18001d90e  mov     ebx, 1
0x18001d913  test    edx, edx
0x18001d915  jz      short loc_18001D920
0x18001d917  test    r9, r9
0x18001d91a  jnz     loc_18001E3CE
0x18001d920  mov     cl, bl
0x18001d922  movd    edx, xmm6
0x18001d926  lea     rdi, [rsp+2F0h+var_288+8]
0x18001d92b  lea     rax, [rbp+1F0h+var_270]
0x18001d92f  test    cl, cl
0x18001d931  cmovnz  rdi, rax
0x18001d935  mov     ecx, 4
0x18001d93a  mov     r14d, 0FF00h
0x18001d940  cmp     edx, ecx
0x18001d942  jb      loc_18001E3AB
0x18001d948  cmp     [r15+74h], r13b
0x18001d94c  jz      loc_18001E3AB
0x18001d952  mov     esi, [rdi]
0x18001d954  mov     eax, [rdi+4]
0x18001d957  mov     rbx, [rdi+8]
0x18001d95b  cmp     esi, ecx
0x18001d95d  jb      loc_18001E62C
0x18001d963  mov     [rsp+2F0h+Destination], r13d
0x18001d968  mov     r9d, ecx; SourceSize
0x18001d96b  mov     r8, rbx; Source
0x18001d96e  mov     edx, ecx; DestinationSize
0x18001d970  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18001d975  call    cs:__imp_memmove_s
0x18001d97b  test    rbx, rbx
0x18001d97e  jz      loc_18001E315
0x18001d984  lea     rcx, [rbx+4]
0x18001d988  lea     rdx, [rbx+rsi]
0x18001d98c  cmp     rdx, rcx
0x18001d98f  jz      loc_18001E315
0x18001d995  cmp     rbx, rcx
0x18001d998  ja      loc_18001E663
0x18001d99e  cmp     rcx, rdx
0x18001d9a1  ja      loc_18001E663
0x18001d9a7  sub     edx, ecx
0x18001d9a9  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001d9ad  xor     eax, eax
0x18001d9af  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001d9b3  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001d9b8  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x18001d9bd  movdqu  xmmword ptr [rdi], xmm0
0x18001d9c1  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x18001d9c8  cmp     word ptr [rsp+2F0h+var_2A0], r14w
0x18001d9ce  jz      loc_18001E6AD
0x18001d9d4  cmp     [rsp+2F0h+Destination], 2014B50h
0x18001d9dc  jnz     loc_18001E597
0x18001d9e2  mov     dword ptr [r15+70h], 2Eh ; '.'
0x18001d9ea  mov     rsi, [rsp+2F0h+var_278]
0x18001d9ef  mov     edi, dword ptr [rsp+2F0h+var_288+8]
0x18001d9f3  test    edi, edi
0x18001d9f5  jz      short loc_18001DA0D
0x18001d9f7  test    rsi, rsi
0x18001d9fa  jnz     loc_18001E6BC
0x18001da00  test    edi, edi
0x18001da02  jz      short loc_18001DA0D
0x18001da04  test    rsi, rsi
0x18001da07  jnz     loc_18001E3BD
0x18001da0d  mov     r14d, dword ptr [rbp+1F0h+var_270]
0x18001da11  cmp     r14d, 2Ah ; '*'
0x18001da15  jb      loc_18001EAA5
0x18001da1b  mov     r8d, dword ptr [rsp+2F0h+var_288]
0x18001da20  mov     r10d, dword ptr [rsp+2F0h+var_290]
0x18001da25  mov     ebx, 1
0x18001da2a  mov     [rsp+2F0h+var_2A0], r13d
0x18001da2f  mov     dword ptr [rsp+2F0h+var_288], r13d
0x18001da34  test    edi, edi
0x18001da36  jz      short loc_18001DA41
0x18001da38  test    rsi, rsi
0x18001da3b  jnz     loc_18001E6CA
0x18001da41  mov     al, bl
0x18001da43  mov     ecx, r14d
0x18001da46  lea     rbx, [rsp+2F0h+var_288+8]
0x18001da4b  lea     rdx, [rbp+1F0h+var_270]
0x18001da4f  test    al, al
0x18001da51  cmovnz  rbx, rdx
0x18001da55  cmp     ecx, 2Ah ; '*'
0x18001da58  jb      loc_18001DE57
0x18001da5e  mov     esi, [rbx]
0x18001da60  mov     eax, [rbx+4]
0x18001da63  mov     rdi, [rbx+8]
0x18001da67  mov     r14d, 2
0x18001da6d  cmp     esi, r14d
0x18001da70  jb      loc_18001E6D4
0x18001da76  mov     word ptr [rsp+2F0h+Destination], r13w
0x18001da7c  mov     r9d, r14d; SourceSize
0x18001da7f  mov     r8, rdi; Source
0x18001da82  mov     edx, r14d; DestinationSize
0x18001da85  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18001da8a  call    cs:__imp_memmove_s
0x18001da90  test    rdi, rdi
0x18001da93  jz      loc_18001E351
0x18001da99  lea     rcx, [rdi+2]
0x18001da9d  lea     rdx, [rdi+rsi]
0x18001daa1  cmp     rdx, rcx
0x18001daa4  jz      loc_18001E351
0x18001daaa  cmp     rdi, rcx
0x18001daad  ja      loc_18001E710
0x18001dab3  cmp     rcx, rdx
0x18001dab6  ja      loc_18001E710
0x18001dabc  sub     edx, ecx
0x18001dabe  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001dac2  xor     eax, eax
0x18001dac4  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001dac8  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001dacd  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x18001dad2  movdqu  xmmword ptr [rbx], xmm0
0x18001dad6  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x18001dadd  mov     eax, 0FF00h
0x18001dae2  cmp     word ptr [rsp+2F0h+var_2A0], ax
0x18001dae7  jz      loc_18001E75A
0x18001daed  mov     cl, byte ptr [rsp+2F0h+Destination]
0x18001daf1  mov     [rbp+1F0h+var_123], cl
0x18001daf7  movzx   eax, word ptr [rsp+2F0h+Destination]
0x18001dafc  shr     eax, 8
0x18001daff  mov     [rbp+1F0h+var_170], eax
0x18001db05  movdqu  [rbp+1F0h+var_250], xmm0
0x18001db0a  lea     rax, [rsp+2F0h+var_288+4]
0x18001db0f  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18001db14  lea     r9, [rsp+2F0h+var_298]
0x18001db19  mov     r8, rbx
0x18001db1c  lea     rdx, [rbp+1F0h+var_250]
0x18001db20  lea     rcx, [rbp+1F0h+var_1F0]
0x18001db24  call    ?readFileHeaderCommon@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU4@PEAG3@Z; win_musl::consumption::readFileHeaderCommon(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,ushort *,ushort *)
0x18001db29  mov     esi, [rbx]
0x18001db2b  mov     eax, [rbx+4]
0x18001db2e  mov     rdi, [rbx+8]
0x18001db32  cmp     esi, r14d
0x18001db35  jb      loc_18001E76F
0x18001db3b  mov     word ptr [rsp+2F0h+Destination], r13w
0x18001db41  mov     r9, r14; SourceSize
0x18001db44  mov     r8, rdi; Source
0x18001db47  mov     rdx, r14; DestinationSize
0x18001db4a  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18001db4f  call    cs:__imp_memmove_s
0x18001db55  test    rdi, rdi
0x18001db58  jz      loc_18001E360
0x18001db5e  lea     rcx, [rdi+2]
0x18001db62  lea     rdx, [rdi+rsi]
0x18001db66  cmp     rdx, rcx
0x18001db69  jz      loc_18001E360
0x18001db6f  cmp     rdi, rcx
0x18001db72  ja      loc_18001E7AB
0x18001db78  cmp     rcx, rdx
0x18001db7b  ja      loc_18001E7AB
0x18001db81  sub     edx, ecx
0x18001db83  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001db87  xor     eax, eax
0x18001db89  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001db8d  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001db92  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x18001db97  movdqu  xmmword ptr [rbx], xmm0
0x18001db9b  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x18001dba2  mov     eax, 0FF00h
0x18001dba7  cmp     word ptr [rsp+2F0h+var_2A0], ax
0x18001dbac  jz      loc_18001E7F5
0x18001dbb2  mov     esi, [rbx]
0x18001dbb4  mov     eax, [rbx+4]
0x18001dbb7  mov     rdi, [rbx+8]
0x18001dbbb  cmp     esi, r14d
0x18001dbbe  jb      loc_18001E80A
0x18001dbc4  mov     word ptr [rsp+2F0h+var_2A0], r13w
0x18001dbca  mov     r9, r14; SourceSize
0x18001dbcd  mov     r8, rdi; Source
0x18001dbd0  mov     rdx, r14; DestinationSize
0x18001dbd3  lea     rcx, [rsp+2F0h+var_2A0]; Destination
0x18001dbd8  call    cs:__imp_memmove_s
0x18001dbde  test    rdi, rdi
0x18001dbe1  jz      loc_18001E36F
0x18001dbe7  lea     rcx, [rdi+2]
0x18001dbeb  lea     rdx, [rdi+rsi]
0x18001dbef  cmp     rdx, rcx
0x18001dbf2  jz      loc_18001E36F
0x18001dbf8  cmp     rdi, rcx
0x18001dbfb  ja      loc_18001E846
0x18001dc01  cmp     rcx, rdx
0x18001dc04  ja      loc_18001E846
0x18001dc0a  sub     edx, ecx
0x18001dc0c  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001dc10  xor     eax, eax
0x18001dc12  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001dc16  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001dc1b  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x18001dc20  movdqu  xmmword ptr [rbx], xmm0
0x18001dc24  mov     word ptr [rsp+2F0h+var_290], 0FFh
0x18001dc2b  mov     eax, 0FF00h
0x18001dc30  cmp     word ptr [rsp+2F0h+var_290], ax
0x18001dc35  jz      loc_18001E890
0x18001dc3b  movzx   eax, word ptr [rsp+2F0h+var_2A0]
0x18001dc40  mov     dword ptr [rsp+2F0h+var_288], eax
0x18001dc44  mov     esi, [rbx]
0x18001dc46  mov     eax, [rbx+4]
0x18001dc49  mov     rdi, [rbx+8]
0x18001dc4d  cmp     esi, r14d
0x18001dc50  jb      loc_18001E8A5
0x18001dc56  mov     word ptr [rsp+2F0h+var_290], r13w
0x18001dc5c  mov     r9, r14; SourceSize
0x18001dc5f  mov     r8, rdi; Source
0x18001dc62  mov     rdx, r14; DestinationSize
0x18001dc65  lea     rcx, [rsp+2F0h+var_290]; Destination
0x18001dc6a  call    cs:__imp_memmove_s
0x18001dc70  test    rdi, rdi
0x18001dc73  jz      loc_18001E37E
0x18001dc79  lea     rcx, [rdi+2]
0x18001dc7d  lea     rdx, [rdi+rsi]
0x18001dc81  cmp     rdx, rcx
0x18001dc84  jz      loc_18001E37E
0x18001dc8a  cmp     rdi, rcx
0x18001dc8d  ja      loc_18001E8E1
0x18001dc93  cmp     rcx, rdx
0x18001dc96  ja      loc_18001E8E1
0x18001dc9c  sub     edx, ecx
0x18001dc9e  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x18001dca2  xor     eax, eax
0x18001dca4  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18001dca8  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18001dcad  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x18001dcb2  movdqu  xmmword ptr [rbx], xmm0
0x18001dcb6  mov     esi, [rbx]
0x18001dcb8  mov     eax, [rbx+4]
0x18001dcbb  mov     rdi, [rbx+8]
  ... truncated ...
```
