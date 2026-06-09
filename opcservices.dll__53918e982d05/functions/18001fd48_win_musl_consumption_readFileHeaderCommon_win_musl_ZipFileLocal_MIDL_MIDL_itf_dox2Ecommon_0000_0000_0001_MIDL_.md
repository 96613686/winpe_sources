# win_musl::consumption::readFileHeaderCommon(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,ushort *,ushort *)

- ea: `0x18001fd48`
- end: `0x180020c0f`
- name: `?readFileHeaderCommon@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU4@PEAG3@Z`
- size: `3783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d7d8`
- `0x180084ea0`

## callees

- `0x180017320`
- `0x18001fd48`
- `0x18002db70`
- `0x18004ebbc`
- `0x180060c90`
- `0x180084010`
- `0x1800b6f0c`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001fdc2`
- `msvcrt!memmove_s` at `0x18001fe68`
- `msvcrt!memmove_s` at `0x18001fefa`
- `msvcrt!memmove_s` at `0x18001ffa1`
- `msvcrt!memmove_s` at `0x18002003b`
- `msvcrt!memmove_s` at `0x1800200d6`
- `msvcrt!memmove_s` at `0x18002017a`
- `msvcrt!memmove_s` at `0x18002021e`
- `msvcrt!memmove_s` at `0x1800202bd`
- `msvcrt!memmove_s` at `0x180020356`
- `msvcrt!memmove_s` at `0x18001fdc2`
- `msvcrt!memmove_s` at `0x18001fe68`
- `msvcrt!memmove_s` at `0x18001fefa`
- `msvcrt!memmove_s` at `0x18001ffa1`
- `msvcrt!memmove_s` at `0x18002003b`
- `msvcrt!memmove_s` at `0x1800200d6`
- `msvcrt!memmove_s` at `0x18002017a`
- `msvcrt!memmove_s` at `0x18002021e`
- `msvcrt!memmove_s` at `0x1800202bd`
- `msvcrt!memmove_s` at `0x180020356`

## string_xrefs

- `0x1800209ef`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020a2a`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020a65`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020aa0`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020adb`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020b16`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020b51`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020b8c`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020bc7`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020c02`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180020516`: `win_musl::detail::vector_read`
- `0x18002056f`: `win_musl::detail::vector_read`
- `0x1800205ca`: `win_musl::detail::vector_read`
- `0x1800206b4`: `win_musl::detail::vector_read`
- `0x18002070d`: `win_musl::detail::vector_read`
- `0x180020766`: `win_musl::detail::vector_read`
- `0x1800207b9`: `win_musl::detail::vector_read`
- `0x18002080c`: `win_musl::detail::vector_read`
- `0x18002085f`: `win_musl::detail::vector_read`
- `0x1800208b8`: `win_musl::detail::vector_read`
- `0x1800209e3`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020a1e`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020a59`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020a94`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020acf`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020b0a`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020b45`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020b80`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020bbb`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020bf6`: `win_musl::consumption::readFileHeaderCommon`
- `0x180020a8d`: `compressed`
- `0x180020610`: `Unsupported file compression (%{Option}): Only Deflate and Store compression options are supported`
- `0x180020a52`: `uncompressed`
- `0x18002097d`: `central directory encryption unsupported `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall win_musl::consumption::readFileHeaderCommon(
        __int64 a1,
        unsigned int *a2,
        _OWORD *a3,
        _WORD *a4,
        _WORD *a5)
{
  __int64 v9; // rsi
  unsigned int v10; // eax
  char *v11; // rdi
  char *v12; // rcx
  char *v13; // rdx
  char v14; // cl
  __int64 v15; // rsi
  unsigned int v16; // eax
  char *v17; // rdi
  char *v18; // rcx
  char *v19; // rdx
  char v20; // r15
  __int64 v21; // rsi
  unsigned int v22; // eax
  char *v23; // rdi
  char *v24; // rcx
  char *v25; // rdx
  int v26; // eax
  __int64 v27; // rsi
  unsigned int v28; // eax
  char *v29; // rdi
  char *v30; // rcx
  char *v31; // rdx
  __int64 v32; // rsi
  unsigned int v33; // eax
  char *v34; // rdi
  char *v35; // rcx
  char *v36; // rdx
  __int64 v37; // rsi
  unsigned int v38; // eax
  char *v39; // rdi
  char *v40; // rcx
  char *v41; // rdx
  unsigned int v42; // eax
  __int64 v43; // rsi
  unsigned int v44; // eax
  char *v45; // rdi
  char *v46; // rcx
  char *v47; // rdx
  __int64 v48; // rsi
  unsigned int v49; // eax
  char *v50; // rdi
  char *v51; // rcx
  char *v52; // rdx
  __int64 v53; // rsi
  unsigned int v54; // eax
  char *v55; // rdi
  char *v56; // rcx
  char *v57; // rdx
  __int64 v58; // rsi
  unsigned int v59; // eax
  char *v60; // rdi
  char *v61; // rcx
  char *v62; // rdx
  __int128 v63; // xmm0
  unsigned __int16 v64; // cx
  unsigned __int16 v65; // cx
  char result; // al
  __int16 v67; // cx
  __int64 v68; // rbx
  win_musl::Formatter *v69; // rax
  struct win_musl::TStringEllipseBase *v70; // rax
  unsigned int v71; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Destination[6]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v73; // [rsp+50h] [rbp-B0h] BYREF
  int v74; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v75; // [rsp+68h] [rbp-98h]
  __int64 v76; // [rsp+70h] [rbp-90h]
  _BYTE v77[160]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v78[40]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v79[40]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+170h] [rbp+70h] BYREF

  v76 = -2;
  v75 = a5;
  v9 = *a2;
  v10 = a2[1];
  v11 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v9 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v10;
    *((_QWORD *)&v73 + 1) = v11;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      41,
      "win_musl::consumption::readFileHeaderCommon",
      "OsAndVersion",
      2,
      &v73);
  }
  Destination[0] = 0;
  memmove_s(Destination, 2u, v11, 2u);
  if ( !v11 || (v12 = v11 + 2, v13 = &v11[v9], &v11[v9] == v11 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v11 > v12 || v12 > v13 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v13 - (_DWORD)v12);
    *((_QWORD *)&v73 + 1) = v11 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v71) = 255;
  v14 = Destination[0];
  *(_DWORD *)(a1 + 200) = HIBYTE(Destination[0]);
  *(_BYTE *)(a1 + 204) = v14;
  v15 = *a2;
  v16 = a2[1];
  v17 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v15 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v16;
    *((_QWORD *)&v73 + 1) = v17;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      48,
      "win_musl::consumption::readFileHeaderCommon",
      "generalPurposeBitFlag",
      2,
      &v73);
  }
  Destination[0] = 0;
  memmove_s(Destination, 2u, v17, 2u);
  if ( !v17 || (v18 = v17 + 2, v19 = &v17[v15], &v17[v15] == v17 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v17 > v18 || v18 > v19 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v19 - (_DWORD)v18);
    *((_QWORD *)&v73 + 1) = v17 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v71) = 255;
  v20 = Destination[0];
  v21 = *a2;
  v22 = a2[1];
  v23 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v21 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v22;
    *((_QWORD *)&v73 + 1) = v23;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      52,
      "win_musl::consumption::readFileHeaderCommon",
      "method",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v23, 2u);
  if ( !v23 || (v24 = v23 + 2, v25 = &v23[v21], &v23[v21] == v23 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v23 > v24 || v24 > v25 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v25 - (_DWORD)v24);
    *((_QWORD *)&v73 + 1) = v23 + 2;
  }
  *(_OWORD *)a2 = v73;
  v26 = (unsigned __int16)v71;
  v74 = (unsigned __int16)v71;
  *(_DWORD *)(a1 + 140) = (unsigned __int16)v71;
  if ( v26 && v26 != 8 )
  {
    std::wstring::wstring(
      v78,
      L"Unsupported file compression (%{Option}): Only Deflate and Store compression options are supported",
      0);
    v68 = win_musl::Formatter::Formatter(pExceptionObject, v78);
    std::wstring::wstring(v79, L"Option");
    v69 = (win_musl::Formatter *)win_musl::Formatter::insert<unsigned int>(v68, v79, &v74);
    v70 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v69);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0x41u,
      0x80511008,
      v70);
    throw (SplException::THResultException *)v77;
  }
  v27 = *a2;
  v28 = a2[1];
  v29 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v27 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v28;
    *((_QWORD *)&v73 + 1) = v29;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      69,
      "win_musl::consumption::readFileHeaderCommon",
      "entry->header.timeLastModified",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v29, 2u);
  if ( !v29 || (v30 = v29 + 2, v31 = &v29[v27], &v29[v27] == v29 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v29 > v30 || v30 > v31 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v31 - (_DWORD)v30);
    *((_QWORD *)&v73 + 1) = v29 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_WORD *)(a1 + 144) = v71;
  v32 = *a2;
  v33 = a2[1];
  v34 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v32 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v33;
    *((_QWORD *)&v73 + 1) = v34;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      72,
      "win_musl::consumption::readFileHeaderCommon",
      "entry->header.dateLastModified",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v34, 2u);
  if ( !v34 || (v35 = v34 + 2, v36 = &v34[v32], &v34[v32] == v34 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v34 > v35 || v35 > v36 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v36 - (_DWORD)v35);
    *((_QWORD *)&v73 + 1) = v34 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_WORD *)(a1 + 146) = v71;
  v37 = *a2;
  v38 = a2[1];
  v39 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v37 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v38;
    *((_QWORD *)&v73 + 1) = v39;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      76,
      "win_musl::consumption::readFileHeaderCommon",
      "crc",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v39, 4u);
  if ( !v39 || (v40 = v39 + 4, v41 = &v39[v37], &v39[v37] == v39 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v39 > v40 || v40 > v41 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v41 - (_DWORD)v40);
    *((_QWORD *)&v73 + 1) = v39 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  v42 = v71;
  *(_DWORD *)(a1 + 192) = 2;
  *(_DWORD *)(a1 + 196) = v42;
  v43 = *a2;
  v44 = a2[1];
  v45 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v43 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v44;
    *((_QWORD *)&v73 + 1) = v45;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      81,
      "win_musl::consumption::readFileHeaderCommon",
      "compressed",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v45, 4u);
  if ( !v45 || (v46 = v45 + 4, v47 = &v45[v43], &v45[v43] == v45 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v45 > v46 || v46 > v47 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v47 - (_DWORD)v46);
    *((_QWORD *)&v73 + 1) = v45 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_QWORD *)(a1 + 168) = 2;
  *(_QWORD *)(a1 + 176) = v71;
  v48 = *a2;
  v49 = a2[1];
  v50 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v48 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v49;
    *((_QWORD *)&v73 + 1) = v50;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      86,
      "win_musl::consumption::readFileHeaderCommon",
      "uncompressed",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v50, 4u);
  if ( !v50 || (v51 = v50 + 4, v52 = &v50[v48], &v50[v48] == v50 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v50 > v51 || v51 > v52 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v52 - (_DWORD)v51);
    *((_QWORD *)&v73 + 1) = v50 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_QWORD *)(a1 + 152) = 2;
  *(_QWORD *)(a1 + 160) = v71;
  v53 = *a2;
  v54 = a2[1];
  v55 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v53 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v54;
    *((_QWORD *)&v73 + 1) = v55;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      90,
      "win_musl::consumption::readFileHeaderCommon",
      "*bytesNeededName",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v55, 2u);
  if ( !v55 || (v56 = v55 + 2, v57 = &v55[v53], &v55[v53] == v55 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v55 > v56 || v56 > v57 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v57 - (_DWORD)v56);
    *((_QWORD *)&v73 + 1) = v55 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *a4 = v71;
  v58 = *a2;
  v59 = a2[1];
  v60 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v58 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v59;
    *((_QWORD *)&v73 + 1) = v60;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      93,
      "win_musl::consumption::readFileHeaderCommon",
      "*bytesNeededExtra",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v60, 2u);
  if ( !v60 || (v61 = v60 + 2, v62 = &v60[v58], &v60[v58] == v60 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v60 > v61 || v61 > v62 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v62 - (_DWORD)v61);
    *((_QWORD *)&v73 + 1) = v60 + 2;
  }
  v63 = v73;
  LOWORD(v74) = 255;
  *v75 = v71;
  if ( (v20 & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0x65u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Unsupported file type: it is Encrypted");
    throw (SplException::THResultException *)v77;
  }
  v64 = Destination[0] >> 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 140) - 8) <= 1 )
    *(_DWORD *)(a1 + 136) = v64 & 3;
  v65 = v64 >> 2;
  result = v65 & 1;
  *(_BYTE *)(a1 + 206) = v65 & 1;
  v67 = v65 >> 3;
  if ( (v67 & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0xA4u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"file encryption unsupported");
    throw (SplException::THResultException *)v77;
  }
  if ( (v67 & 0x80u) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0xC0u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"central directory encryption unsupported ");
    throw (SplException::THResultException *)v77;
  }
  *a3 = v63;
  return result;
}

```

## disassembly

```asm
0x18001fd48  push    rbp
0x18001fd4a  push    rbx
0x18001fd4b  push    rsi
0x18001fd4c  push    rdi
0x18001fd4d  push    r12
0x18001fd4f  push    r13
0x18001fd51  push    r14
0x18001fd53  push    r15
0x18001fd55  lea     rbp, [rsp-128h]
0x18001fd5d  sub     rsp, 228h
0x18001fd64  mov     [rsp+260h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x18001fd6d  mov     rax, cs:__security_cookie
0x18001fd74  xor     rax, rsp
0x18001fd77  mov     [rbp+160h+var_50], rax
0x18001fd7e  mov     r12, r9
0x18001fd81  mov     r13, r8
0x18001fd84  mov     rbx, rdx
0x18001fd87  mov     r14, rcx
0x18001fd8a  mov     rax, [rbp+160h+arg_20]
0x18001fd91  mov     [rsp+260h+var_1F8], rax
0x18001fd96  mov     esi, [rdx]
0x18001fd98  mov     eax, [rdx+4]
0x18001fd9b  mov     rdi, [rdx+8]
0x18001fd9f  mov     ecx, 2
0x18001fda4  cmp     esi, ecx
0x18001fda6  jb      loc_180020BD4
0x18001fdac  xor     r15d, r15d
0x18001fdaf  mov     [rsp+260h+Destination], r15w
0x18001fdb5  mov     r9d, ecx; SourceSize
0x18001fdb8  mov     r8, rdi; Source
0x18001fdbb  mov     edx, ecx; DestinationSize
0x18001fdbd  lea     rcx, [rsp+260h+Destination]; Destination
0x18001fdc2  call    cs:__imp_memmove_s
0x18001fdc8  test    rdi, rdi
0x18001fdcb  jz      loc_18002043C
0x18001fdd1  lea     rcx, [rdi+2]
0x18001fdd5  lea     rdx, [rdi+rsi]
0x18001fdd9  cmp     rdx, rcx
0x18001fddc  jz      loc_18002043C
0x18001fde2  cmp     rdi, rcx
0x18001fde5  ja      loc_1800204FA
0x18001fdeb  cmp     rcx, rdx
0x18001fdee  ja      loc_1800204FA
0x18001fdf4  sub     edx, ecx
0x18001fdf6  mov     dword ptr [rsp+260h+var_210], edx
0x18001fdfa  xor     eax, eax
0x18001fdfc  mov     dword ptr [rsp+260h+var_210+4], eax
0x18001fe00  mov     qword ptr [rsp+260h+var_210+8], rcx
0x18001fe05  movups  xmm0, [rsp+260h+var_210]
0x18001fe0a  movdqu  xmmword ptr [rbx], xmm0
0x18001fe0e  mov     word ptr [rsp+260h+var_220], 0FFh
0x18001fe15  mov     eax, 0FF00h
0x18001fe1a  cmp     word ptr [rsp+260h+var_220], ax
0x18001fe1f  jz      loc_18002053E
0x18001fe25  mov     cl, byte ptr [rsp+260h+Destination]
0x18001fe29  movzx   eax, [rsp+260h+Destination]
0x18001fe2e  shr     eax, 8
0x18001fe31  mov     [r14+0C8h], eax
0x18001fe38  mov     [r14+0CCh], cl
0x18001fe3f  mov     esi, [rbx]
0x18001fe41  mov     eax, [rbx+4]
0x18001fe44  mov     rdi, [rbx+8]
0x18001fe48  mov     ecx, 2
0x18001fe4d  cmp     esi, ecx
0x18001fe4f  jb      loc_180020B99
0x18001fe55  mov     [rsp+260h+Destination], r15w
0x18001fe5b  mov     r9d, ecx; SourceSize
0x18001fe5e  mov     r8, rdi; Source
0x18001fe61  mov     edx, ecx; DestinationSize
0x18001fe63  lea     rcx, [rsp+260h+Destination]; Destination
0x18001fe68  call    cs:__imp_memmove_s
0x18001fe6e  test    rdi, rdi
0x18001fe71  jz      loc_18002044B
0x18001fe77  lea     rcx, [rdi+2]
0x18001fe7b  lea     rdx, [rdi+rsi]
0x18001fe7f  cmp     rdx, rcx
0x18001fe82  jz      loc_18002044B
0x18001fe88  cmp     rdi, rcx
0x18001fe8b  ja      loc_180020553
0x18001fe91  cmp     rcx, rdx
0x18001fe94  ja      loc_180020553
0x18001fe9a  sub     edx, ecx
0x18001fe9c  mov     dword ptr [rsp+260h+var_210], edx
0x18001fea0  xor     eax, eax
0x18001fea2  mov     dword ptr [rsp+260h+var_210+4], eax
0x18001fea6  mov     qword ptr [rsp+260h+var_210+8], rcx
0x18001feab  movups  xmm0, [rsp+260h+var_210]
0x18001feb0  movdqu  xmmword ptr [rbx], xmm0
0x18001feb4  mov     word ptr [rsp+260h+var_220], 0FFh
0x18001febb  mov     eax, 0FF00h
0x18001fec0  cmp     word ptr [rsp+260h+var_220], ax
0x18001fec5  jz      loc_180020597
0x18001fecb  mov     r15b, byte ptr [rsp+260h+Destination]
0x18001fed0  mov     esi, [rbx]
0x18001fed2  mov     eax, [rbx+4]
0x18001fed5  mov     rdi, [rbx+8]
0x18001fed9  mov     ecx, 2
0x18001fede  cmp     esi, ecx
0x18001fee0  jb      loc_180020B5E
0x18001fee6  xor     eax, eax
0x18001fee8  mov     word ptr [rsp+260h+var_220], ax
0x18001feed  mov     r9d, ecx; SourceSize
0x18001fef0  mov     r8, rdi; Source
0x18001fef3  mov     edx, ecx; DestinationSize
0x18001fef5  lea     rcx, [rsp+260h+var_220]; Destination
0x18001fefa  call    cs:__imp_memmove_s
0x18001ff00  xor     r8d, r8d
0x18001ff03  test    rdi, rdi
0x18001ff06  jz      loc_18002045A
0x18001ff0c  lea     rcx, [rdi+2]
0x18001ff10  lea     rdx, [rdi+rsi]
0x18001ff14  cmp     rdx, rcx
0x18001ff17  jz      loc_18002045A
0x18001ff1d  cmp     rdi, rcx
0x18001ff20  ja      loc_1800205AE
0x18001ff26  cmp     rcx, rdx
0x18001ff29  ja      loc_1800205AE
0x18001ff2f  sub     edx, ecx
0x18001ff31  mov     dword ptr [rsp+260h+var_210], edx
0x18001ff35  xor     eax, eax
0x18001ff37  mov     dword ptr [rsp+260h+var_210+4], eax
0x18001ff3b  mov     qword ptr [rsp+260h+var_210+8], rcx
0x18001ff40  movups  xmm0, [rsp+260h+var_210]
0x18001ff45  movdqu  xmmword ptr [rbx], xmm0
0x18001ff49  mov     word ptr [rsp+260h+var_200], 0FFh
0x18001ff50  mov     eax, 0FF00h
0x18001ff55  cmp     word ptr [rsp+260h+var_200], ax
0x18001ff5a  jz      loc_1800205F2
0x18001ff60  movzx   eax, word ptr [rsp+260h+var_220]
0x18001ff65  mov     [rsp+260h+var_200], eax
0x18001ff69  mov     [r14+8Ch], eax
0x18001ff70  test    eax, eax
0x18001ff72  jnz     loc_180020607
0x18001ff78  mov     esi, [rbx]
0x18001ff7a  mov     eax, [rbx+4]
0x18001ff7d  mov     rdi, [rbx+8]
0x18001ff81  mov     ecx, 2
0x18001ff86  cmp     esi, ecx
0x18001ff88  jb      loc_180020B23
0x18001ff8e  mov     word ptr [rsp+260h+var_220], r8w
0x18001ff94  mov     r9d, ecx; SourceSize
0x18001ff97  mov     r8, rdi; Source
0x18001ff9a  mov     edx, ecx; DestinationSize
0x18001ff9c  lea     rcx, [rsp+260h+var_220]; Destination
0x18001ffa1  call    cs:__imp_memmove_s
0x18001ffa7  test    rdi, rdi
0x18001ffaa  jz      loc_180020469
0x18001ffb0  lea     rcx, [rdi+2]
0x18001ffb4  lea     rdx, [rdi+rsi]
0x18001ffb8  cmp     rdx, rcx
0x18001ffbb  jz      loc_180020469
0x18001ffc1  cmp     rdi, rcx
0x18001ffc4  ja      loc_180020698
0x18001ffca  cmp     rcx, rdx
0x18001ffcd  ja      loc_180020698
0x18001ffd3  sub     edx, ecx
0x18001ffd5  mov     dword ptr [rsp+260h+var_210], edx
0x18001ffd9  xor     eax, eax
0x18001ffdb  mov     dword ptr [rsp+260h+var_210+4], eax
0x18001ffdf  mov     qword ptr [rsp+260h+var_210+8], rcx
0x18001ffe4  movups  xmm0, [rsp+260h+var_210]
0x18001ffe9  movdqu  xmmword ptr [rbx], xmm0
0x18001ffed  mov     word ptr [rsp+260h+var_200], 0FFh
0x18001fff4  mov     eax, 0FF00h
0x18001fff9  cmp     word ptr [rsp+260h+var_200], ax
0x18001fffe  jz      loc_1800206DC
0x180020004  movzx   eax, word ptr [rsp+260h+var_220]
0x180020009  mov     [r14+90h], ax
0x180020011  mov     esi, [rbx]
0x180020013  mov     eax, [rbx+4]
0x180020016  mov     rdi, [rbx+8]
0x18002001a  mov     ecx, 2
0x18002001f  cmp     esi, ecx
0x180020021  jb      loc_180020AE8
0x180020027  xor     eax, eax
0x180020029  mov     word ptr [rsp+260h+var_220], ax
0x18002002e  mov     r9d, ecx; SourceSize
0x180020031  mov     r8, rdi; Source
0x180020034  mov     edx, ecx; DestinationSize
0x180020036  lea     rcx, [rsp+260h+var_220]; Destination
0x18002003b  call    cs:__imp_memmove_s
0x180020041  xor     r8d, r8d
0x180020044  test    rdi, rdi
0x180020047  jz      loc_180020480
0x18002004d  lea     rcx, [rdi+2]
0x180020051  lea     rdx, [rdi+rsi]
0x180020055  cmp     rdx, rcx
0x180020058  jz      loc_180020480
0x18002005e  cmp     rdi, rcx
0x180020061  ja      loc_1800206F1
0x180020067  cmp     rcx, rdx
0x18002006a  ja      loc_1800206F1
0x180020070  sub     edx, ecx
0x180020072  mov     dword ptr [rsp+260h+var_210], edx
0x180020076  xor     eax, eax
0x180020078  mov     dword ptr [rsp+260h+var_210+4], eax
0x18002007c  mov     qword ptr [rsp+260h+var_210+8], rcx
0x180020081  movups  xmm0, [rsp+260h+var_210]
0x180020086  movdqu  xmmword ptr [rbx], xmm0
0x18002008a  mov     word ptr [rsp+260h+var_200], 0FFh
0x180020091  mov     eax, 0FF00h
0x180020096  cmp     word ptr [rsp+260h+var_200], ax
0x18002009b  jz      loc_180020735
0x1800200a1  movzx   eax, word ptr [rsp+260h+var_220]
0x1800200a6  mov     [r14+92h], ax
0x1800200ae  mov     esi, [rbx]
0x1800200b0  mov     eax, [rbx+4]
0x1800200b3  mov     rdi, [rbx+8]
0x1800200b7  mov     ecx, 4
0x1800200bc  cmp     esi, ecx
0x1800200be  jb      loc_180020AAD
0x1800200c4  mov     [rsp+260h+var_220], r8d
0x1800200c9  mov     r9d, ecx; SourceSize
0x1800200cc  mov     r8, rdi; Source
0x1800200cf  mov     edx, ecx; DestinationSize
0x1800200d1  lea     rcx, [rsp+260h+var_220]; Destination
0x1800200d6  call    cs:__imp_memmove_s
0x1800200dc  test    rdi, rdi
0x1800200df  jz      loc_18002048F
0x1800200e5  lea     rcx, [rdi+4]
0x1800200e9  lea     rdx, [rdi+rsi]
0x1800200ed  cmp     rdx, rcx
0x1800200f0  jz      loc_18002048F
0x1800200f6  cmp     rdi, rcx
0x1800200f9  ja      loc_18002074A
0x1800200ff  cmp     rcx, rdx
0x180020102  ja      loc_18002074A
0x180020108  sub     edx, ecx
0x18002010a  mov     dword ptr [rsp+260h+var_210], edx
0x18002010e  xor     eax, eax
0x180020110  mov     dword ptr [rsp+260h+var_210+4], eax
0x180020114  mov     qword ptr [rsp+260h+var_210+8], rcx
0x180020119  movups  xmm0, [rsp+260h+var_210]
0x18002011e  movdqu  xmmword ptr [rbx], xmm0
0x180020122  mov     word ptr [rsp+260h+var_200], 0FFh
0x180020129  mov     eax, 0FF00h
0x18002012e  cmp     word ptr [rsp+260h+var_200], ax
0x180020133  jz      loc_18002078E
0x180020139  mov     eax, [rsp+260h+var_220]
0x18002013d  mov     dword ptr [r14+0C0h], 2
0x180020148  mov     [r14+0C4h], eax
0x18002014f  mov     esi, [rbx]
0x180020151  mov     eax, [rbx+4]
0x180020154  mov     rdi, [rbx+8]
0x180020158  mov     ecx, 4
0x18002015d  cmp     esi, ecx
0x18002015f  jb      loc_180020A72
0x180020165  mov     [rsp+260h+var_220], 0
0x18002016d  mov     r9d, ecx; SourceSize
0x180020170  mov     r8, rdi; Source
0x180020173  mov     edx, ecx; DestinationSize
0x180020175  lea     rcx, [rsp+260h+var_220]; Destination
0x18002017a  call    cs:__imp_memmove_s
0x180020180  test    rdi, rdi
0x180020183  jz      loc_1800204A6
0x180020189  lea     rcx, [rdi+4]
0x18002018d  lea     rdx, [rdi+rsi]
0x180020191  cmp     rdx, rcx
0x180020194  jz      loc_1800204A6
0x18002019a  cmp     rdi, rcx
0x18002019d  ja      loc_18002079D
0x1800201a3  cmp     rcx, rdx
0x1800201a6  ja      loc_18002079D
0x1800201ac  sub     edx, ecx
0x1800201ae  mov     dword ptr [rsp+260h+var_210], edx
0x1800201b2  xor     eax, eax
0x1800201b4  mov     dword ptr [rsp+260h+var_210+4], eax
0x1800201b8  mov     qword ptr [rsp+260h+var_210+8], rcx
0x1800201bd  movups  xmm0, [rsp+260h+var_210]
0x1800201c2  movdqu  xmmword ptr [rbx], xmm0
0x1800201c6  mov     word ptr [rsp+260h+var_200], 0FFh
0x1800201cd  mov     eax, 0FF00h
0x1800201d2  cmp     word ptr [rsp+260h+var_200], ax
0x1800201d7  jz      loc_1800207E1
0x1800201dd  mov     qword ptr [r14+0A8h], 2
0x1800201e8  mov     eax, [rsp+260h+var_220]
0x1800201ec  mov     [r14+0B0h], rax
0x1800201f3  mov     esi, [rbx]
0x1800201f5  mov     eax, [rbx+4]
0x1800201f8  mov     rdi, [rbx+8]
0x1800201fc  mov     ecx, 4
0x180020201  cmp     esi, ecx
0x180020203  jb      loc_180020A37
0x180020209  mov     [rsp+260h+var_220], 0
0x180020211  mov     r9d, ecx; SourceSize
0x180020214  mov     r8, rdi; Source
0x180020217  mov     edx, ecx; DestinationSize
0x180020219  lea     rcx, [rsp+260h+var_220]; Destination
0x18002021e  call    cs:__imp_memmove_s
0x180020224  test    rdi, rdi
0x180020227  jz      loc_1800204BD
0x18002022d  lea     rcx, [rdi+4]
0x180020231  lea     rdx, [rdi+rsi]
0x180020235  cmp     rdx, rcx
0x180020238  jz      loc_1800204BD
0x18002023e  cmp     rdi, rcx
0x180020241  ja      loc_1800207F0
0x180020247  cmp     rcx, rdx
0x18002024a  ja      loc_1800207F0
0x180020250  sub     edx, ecx
  ... truncated ...
```
