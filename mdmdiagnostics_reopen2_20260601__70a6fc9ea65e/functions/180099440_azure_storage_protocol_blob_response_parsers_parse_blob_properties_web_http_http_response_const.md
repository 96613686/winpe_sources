# azure::storage::protocol::blob_response_parsers::parse_blob_properties(web::http::http_response const &)

- ea: `0x180099440`
- end: `0x18009a949`
- name: `?parse_blob_properties@blob_response_parsers@protocol@storage@azure@@SA?AVcloud_blob_properties@34@AEBVhttp_response@http@web@@@Z`
- size: `5385`
- prototype: `static struct azure::storage::cloud_blob_properties __high(const struct web::http::http_response *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005b970`
- `0x180073710`

## callees

- `0x180019080`
- `0x180019588`
- `0x18001a084`
- `0x180020f50`
- `0x180072970`
- `0x180096cd0`
- `0x180096e20`
- `0x180097bb0`
- `0x180098640`
- `0x1800987a0`
- `0x1800989f0`
- `0x180098cb0`
- `0x180099440`
- `0x18009a950`
- `0x1800a9dcb`
- `0x1800aa020`
- `0x1800e54e0`
- `0x1800e7050`
- `0x1800e7be0`
- `0x1800eeef0`
- `0x1800efd9c`
- `0x1800f7a78`
- `0x1800fa7d4`
- `0x1801089a8`
- `0x180193010`

## import_xrefs

- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800996b9`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800998d6`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800996b9`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800998d6`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800995c4`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800997e9`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800995c4`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800997e9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800996c3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800998e0`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800996c3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800998e0`
- `msvcp_win!?bad@ios_base@std@@QEBA_NXZ` at `0x180099676`
- `msvcp_win!?bad@ios_base@std@@QEBA_NXZ` at `0x180099894`
- `msvcp_win!?bad@ios_base@std@@QEBA_NXZ` at `0x180099676`
- `msvcp_win!?bad@ios_base@std@@QEBA_NXZ` at `0x180099894`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x180099624`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x180099842`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x180099624`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x180099842`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAH@Z` at `0x18009987d`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAH@Z` at `0x18009987d`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x18009965f`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x18009965f`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800995a5`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800997c7`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800995a5`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800997c7`

## string_xrefs

- `0x180099785`: `x-ms-blob-committed-block-count`
- `0x180099794`: `x-ms-blob-committed-block-count`
- `0x18009a618`: `x-ms-incremental-copy`
- `0x18009a627`: `x-ms-incremental-copy`
- `0x18009a032`: `x-ms-access-tier`
- `0x18009a041`: `x-ms-access-tier`
- `0x18009a701`: `x-ms-access-tier-inferred`
- `0x18009a710`: `x-ms-access-tier-inferred`
- `0x180099f68`: `x-ms-access-tier-change-time`
- `0x180099f77`: `x-ms-access-tier-change-time`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall azure::storage::protocol::blob_response_parsers::parse_blob_properties(
        __int64 a1,
        const struct web::http::http_response *a2)
{
  int v4; // r12d
  __int64 v5; // rax
  void *v6; // rcx
  __int64 v7; // r15
  size_t v8; // rax
  __int64 header_value; // rbx
  char *v10; // rbx
  const struct std::locale *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rax
  __int64 v13; // rbx
  void *v14; // rcx
  void *v15; // rcx
  size_t v16; // rax
  __int64 v17; // rbx
  char v18; // r13
  char *v19; // rbx
  const struct std::locale *v20; // rax
  void (__fastcall ***v21)(_QWORD, __int64); // rax
  int v22; // ebx
  void *v23; // rcx
  void *v24; // rcx
  __int64 v25; // rax
  void *v26; // rcx
  size_t v27; // rax
  __int64 v28; // rax
  void *v29; // rcx
  void *v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  __int64 v33; // rax
  void *v34; // rcx
  __int64 v35; // rax
  void *v36; // rcx
  size_t v37; // rax
  __int64 v38; // rbx
  size_t v39; // rax
  const wchar_t *v40; // rcx
  size_t v41; // rsi
  int v42; // r14d
  size_t v43; // rax
  const wchar_t *v44; // rcx
  size_t v45; // rax
  int v46; // eax
  void *v47; // rcx
  void *v48; // rcx
  size_t v49; // rax
  __int64 v50; // rax
  void *v51; // rcx
  void *v52; // rcx
  bool v53; // bl
  __int64 v54; // rax
  size_t v55; // rax
  void *v56; // rcx
  size_t v57; // rax
  void *v58; // rcx
  size_t v59; // rax
  const wchar_t *v60; // rcx
  int v61; // eax
  size_t v62; // rax
  const wchar_t *v63; // rcx
  size_t v64; // rax
  const wchar_t *v65; // rcx
  size_t v66; // rax
  const wchar_t *v67; // rcx
  size_t v68; // rax
  const wchar_t *v69; // rcx
  size_t v70; // rax
  const wchar_t *v71; // rcx
  size_t v72; // rax
  const wchar_t *v73; // rcx
  size_t v74; // rax
  const wchar_t *v75; // rcx
  size_t v76; // rax
  const wchar_t *v77; // rcx
  size_t v78; // rax
  const wchar_t *v79; // rcx
  size_t v80; // rax
  const wchar_t *v81; // rcx
  size_t v82; // rax
  __int64 v83; // rbx
  size_t v84; // rax
  const wchar_t *v85; // rcx
  size_t *v86; // rsi
  size_t v87; // r8
  size_t v88; // rax
  size_t v89; // r8
  void *v90; // rcx
  void *v91; // rcx
  size_t v92; // rax
  __int64 v93; // rax
  void *v94; // rcx
  void *v95; // rcx
  size_t v96; // rax
  __int64 v97; // rax
  void *v98; // rcx
  void *v99; // rcx
  size_t v100; // rax
  __int64 v101; // rax
  size_t v102; // rax
  __int64 v103; // rax
  size_t v104; // rax
  __int64 v105; // rax
  __int64 v107; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v108[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v109[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v110[120]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v111[96]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v112; // [rsp+120h] [rbp+20h]
  void *Block[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v114; // [rsp+138h] [rbp+38h]
  unsigned __int64 v115; // [rsp+140h] [rbp+40h]
  void *pExceptionObject[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v117; // [rsp+158h] [rbp+58h]
  unsigned __int64 v118; // [rsp+160h] [rbp+60h]
  wchar_t *S1[2]; // [rsp+168h] [rbp+68h] BYREF
  size_t N; // [rsp+178h] [rbp+78h]
  unsigned __int64 v121; // [rsp+180h] [rbp+80h]
  void *v122[2]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v123; // [rsp+198h] [rbp+98h]
  unsigned __int64 v124; // [rsp+1A0h] [rbp+A0h]
  _QWORD v125[4]; // [rsp+1A8h] [rbp+A8h] BYREF

  v112 = a1;
  azure::storage::cloud_blob_properties::cloud_blob_properties((azure::storage::cloud_blob_properties *)a1);
  v4 = 1;
  v5 = azure::storage::protocol::parse_etag(Block, a2);
  std::wstring::operator=(a1 + 200, v5);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v6 = Block[0];
    }
    else
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v6);
  }
  *(_QWORD *)(a1 + 264) = *(_QWORD *)azure::storage::protocol::parse_last_modified(&v107, a2);
  *(_DWORD *)(a1 + 316) = azure::storage::protocol::parse_lease_status(a2);
  *(_DWORD *)(a1 + 320) = azure::storage::protocol::parse_lease_state(a2);
  *(_DWORD *)(a1 + 324) = azure::storage::protocol::parse_lease_duration(a2);
  *(_QWORD *)(a1 + 128) = azure::storage::protocol::blob_response_parsers::parse_blob_size(a2);
  v7 = *(_QWORD *)a2 + 88LL;
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v8 = wcslen_0(L"x-ms-blob-sequence-number");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"x-ms-blob-sequence-number", v8);
  header_value = azure::storage::protocol::get_header_value(Block, v7, v122);
  v108[0] = &std::basic_istringstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(v111);
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(v108, v109, 0, 0, 5);
  *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::basic_stringbuf<unsigned short>(v109, header_value, 1);
  v10 = (char *)v108 + *(int *)(v108[0] + 4LL);
  v11 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v10, pExceptionObject, v11);
  if ( pExceptionObject[1] )
  {
    v12 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(void *))(*(_QWORD *)pExceptionObject[1]
                                                                                    + 16LL))(pExceptionObject[1]);
    if ( v12 )
      (**v12)(v12, 1);
  }
  std::basic_istream<unsigned short>::operator>>(v108, &v107);
  if ( std::ios_base::bad((std::ios_base *)((char *)v108 + *(int *)(v108[0] + 4LL))) )
  {
    std::bad_cast::bad_cast((std::bad_cast *)pExceptionObject);
    throw (std::bad_cast *)pExceptionObject;
  }
  v13 = v107;
  *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v109);
  std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(v110);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v111);
  *(_QWORD *)(a1 + 344) = v13;
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v14 = Block[0];
    }
    else
    {
      v14 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v14);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v15 = v122[0];
    }
    else
    {
      v15 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v15 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v15);
  }
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v16 = wcslen_0(L"x-ms-blob-committed-block-count");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"x-ms-blob-committed-block-count", v16);
  v17 = azure::storage::protocol::get_header_value(Block, v7, v122);
  v108[0] = &std::basic_istringstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(v111);
  v18 = 13;
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(v108, v109, 0, 0, 13);
  *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::basic_stringbuf<unsigned short>(v109, v17, 1);
  v19 = (char *)v108 + *(int *)(v108[0] + 4LL);
  v20 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v19, pExceptionObject, v20);
  if ( pExceptionObject[1] )
  {
    v21 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(void *))(*(_QWORD *)pExceptionObject[1]
                                                                                    + 16LL))(pExceptionObject[1]);
    if ( v21 )
      (**v21)(v21, 1);
  }
  std::basic_istream<unsigned short>::operator>>(v108, &v107);
  if ( std::ios_base::bad((std::ios_base *)((char *)v108 + *(int *)(v108[0] + 4LL))) )
  {
    std::bad_cast::bad_cast((std::bad_cast *)pExceptionObject);
    throw (std::bad_cast *)pExceptionObject;
  }
  v22 = v107;
  *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v109);
  std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(v110);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v111);
  *(_DWORD *)(a1 + 352) = v22;
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v23 = Block[0];
    }
    else
    {
      v23 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v23 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v23);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v24 = v122[0];
    }
    else
    {
      v24 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v24 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v24);
  }
  v25 = azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::cache_control);
  std::wstring::operator=(a1, v25);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v26 = Block[0];
    }
    else
    {
      v26 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v26 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v26);
  }
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v27 = wcslen_0(L"Content-Disposition");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"Content-Disposition", v27);
  v28 = azure::storage::protocol::get_header_value(Block, v7, v122);
  std::wstring::operator=(a1 + 32, v28);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v29 = Block[0];
    }
    else
    {
      v29 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v29 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v29);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v30 = v122[0];
    }
    else
    {
      v30 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v30 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v30);
  }
  v31 = azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::content_encoding);
  std::wstring::operator=(a1 + 64, v31);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v32 = Block[0];
    }
    else
    {
      v32 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v32);
  }
  v33 = azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::content_language);
  std::wstring::operator=(a1 + 96, v33);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v34 = Block[0];
    }
    else
    {
      v34 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v34 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v34);
  }
  v35 = azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::content_type);
  std::wstring::operator=(a1 + 168, v35);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v36 = Block[0];
    }
    else
    {
      v36 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v36 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v36);
  }
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v37 = wcslen_0(L"x-ms-blob-type");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"x-ms-blob-type", v37);
  v38 = azure::storage::protocol::get_header_value(Block, v7, v122);
  v39 = wcslen_0(L"BlockBlob");
  v40 = (const wchar_t *)v38;
  if ( *(_QWORD *)(v38 + 24) > 7u )
    v40 = *(const wchar_t **)v38;
  v41 = *(_QWORD *)(v38 + 16);
  v42 = 3;
  if ( v41 == v39 )
  {
    if ( !v41 || !wmemcmp(v40, L"BlockBlob", *(_QWORD *)(v38 + 16)) )
    {
      v46 = 2;
      goto LABEL_96;
    }
    v41 = *(_QWORD *)(v38 + 16);
  }
  v43 = wcslen_0(L"PageBlob");
  v44 = (const wchar_t *)v38;
  if ( *(_QWORD *)(v38 + 24) > 7u )
    v44 = *(const wchar_t **)v38;
  if ( v41 == v43 )
  {
    if ( !v41 || !wmemcmp(v44, L"PageBlob", v41) )
    {
      v46 = 1;
      goto LABEL_96;
    }
    v41 = *(_QWORD *)(v38 + 16);
  }
  v45 = wcslen_0(L"AppendBlob");
  if ( *(_QWORD *)(v38 + 24) > 7u )
    v38 = *(_QWORD *)v38;
  if ( v41 == v45 && (!v41 || !wmemcmp((const wchar_t *)v38, L"AppendBlob", v41)) )
    v46 = 3;
  else
    v46 = 0;
LABEL_96:
  *(_DWORD *)(a1 + 312) = v46;
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v47 = Block[0];
    }
    else
    {
      v47 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v47 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v47);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v48 = v122[0];
    }
    else
    {
      v48 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v48 - 8) > 0x1F )
        goto LABEL_117;
    }
    operator delete(v48);
  }
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v49 = wcslen_0(L"x-ms-blob-content-md5");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"x-ms-blob-content-md5", v49);
  v50 = azure::storage::protocol::get_header_value(Block, v7, v122);
  std::wstring::operator=(a1 + 136, v50);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v51 = Block[0];
    }
    else
    {
      v51 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v51 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v51);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v52 = v122[0];
    }
    else
    {
      v52 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v52 - 8) > 0x1F )
LABEL_117:
        __fastfail(5u);
    }
    operator delete(v52);
  }
  v53 = 0;
  if ( !*(_QWORD *)(a1 + 152) )
  {
    v18 = 15;
    if ( !*(_QWORD *)(azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::content_range) + 16) )
      v53 = 1;
  }
  if ( (v18 & 2) != 0 )
    std::wstring::_Tidy_deallocate(Block);
  if ( v53 )
  {
    v54 = azure::storage::protocol::get_header_value(Block, v7, &web::http::header_names::content_md5);
    std::wstring::operator=(a1 + 136, v54);
    std::wstring::_Tidy_deallocate(Block);
  }
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v55 = wcslen_0(L"x-ms-access-tier-change-time");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-access-tier-change-time", v55);
  azure::storage::protocol::get_header_value(v125, v7, pExceptionObject);
  if ( v118 > 7 )
  {
    if ( 2 * v118 + 2 < 0x1000 )
    {
      v56 = pExceptionObject[0];
    }
    else
    {
      v56 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
      if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v56 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v56);
  }
  v117 = 0;
  v118 = 7;
  LOWORD(pExceptionObject[0]) = 0;
  if ( v125[2] )
    *(_QWORD *)(a1 + 272) = *(_QWORD *)utility::datetime::from_string(&v107, v125, 0);
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v124 = 0;
  v57 = wcslen_0(L"x-ms-access-tier");
  std::wstring::_Construct<1,unsigned short const *>(v122, L"x-ms-access-tier", v57);
  azure::storage::protocol::get_header_value(S1, v7, v122);
  if ( v124 > 7 )
  {
    if ( 2 * v124 + 2 < 0x1000 )
    {
      v58 = v122[0];
    }
    else
    {
      v58 = (void *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)((char *)v122[0] - (char *)v58 - 8) > 0x1F )
        goto LABEL_254;
    }
    operator delete(v58);
  }
  v123 = 0;
  v124 = 7;
  LOWORD(v122[0]) = 0;
  v59 = wcslen_0(L"Hot");
  v60 = (const wchar_t *)S1;
  if ( v121 > 7 )
    v60 = S1[0];
  if ( N == v59 && (!N || !wmemcmp(v60, L"Hot", N)) )
  {
    v61 = 1;
  }
  else
  {
    v62 = wcslen_0(L"Cool");
    v63 = (const wchar_t *)S1;
    if ( v121 > 7 )
      v63 = S1[0];
    if ( N == v62 && (!N || !wmemcmp(v63, L"Cool", N)) )
    {
      v61 = 2;
    }
    else
    {
      v64 = wcslen_0(L"Archive");
      v65 = (const wchar_t *)S1;
      if ( v121 > 7 )
        v65 = S1[0];
      if ( N == v64 && (!N || !wmemcmp(v65, L"Archive", N)) )
        v61 = 3;
      else
        v61 = 0;
    }
  }
  *(_DWORD *)(a1 + 328) = v61;
  v66 = wcslen_0(L"P4");
  v67 = (const wchar_t *)S1;
  if ( v121 > 7 )
    v67 = S1[0];
  if ( N == v66 && (!N || !wmemcmp(v67, L"P4", N)) )
  {
    v42 = 1;
  }
  else
  {
    v68 = wcslen_0(L"P6");
    v69 = (const wchar_t *)S1;
    if ( v121 > 7 )
      v69 = S1[0];
    if ( N == v68 && (!N || !wmemcmp(v69, L"P6", N)) )
    {
      v42 = 2;
    }
    else
    {
      v70 = wcslen_0(L"P10");
      v71 = (const wchar_t *)S1;
      if ( v121 > 7 )
        v71 = S1[0];
      if ( N != v70 || N && wmemcmp(v71, L"P10", N) )
      {
        v72 = wcslen_0(L"P20");
        v73 = (const wchar_t *)S1;
        if ( v121 > 7 )
          v73 = S1[0];
        if ( N == v72 && (!N || !wmemcmp(v73, L"P20", N)) )
        {
          v42 = 4;
        }
        else
        {
          v74 = wcslen_0(L"P30");
          v75 = (const wchar_t *)S1;
          if ( v121 > 7 )
            v75 = S1[0];
          if ( N == v74 && (!N || !wmemcmp(v75, L"P30", N)) )
          {
            v42 = 5;
          }
          else
          {
            v76 = wcslen_0(L"P40");
            v77 = (const wchar_t *)S1;
            if ( v121 > 7 )
              v77 = S1[0];
            if ( N == v76 && (!N || !wmemcmp(v77, L"P40", N)) )
            {
              v42 = 6;
            }
            else
            {
              v78 = wcslen_0(L"P50");
              v79 = (const wchar_t *)S1;
              if ( v121 > 7 )
                v79 = S1[0];
              if ( N == v78 && (!N || !wmemcmp(v79, L"P50", N)) )
              {
                v42 = 7;
              }
              else
              {
                v80 = wcslen_0(L"P60");
                v81 = (const wchar_t *)S1;
                if ( v121 > 7 )
                  v81 = S1[0];
                if ( N == v80 && (!N || !wmemcmp(v81, L"P60", N)) )
                  v42 = 8;
                else
                  v42 = 0;
              }
            }
          }
        }
      }
    }
  }
  *(_DWORD *)(a1 + 332) = v42;
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v82 = wcslen_0(L"x-ms-archive-status");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-archive-status", v82);
  v83 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  v84 = wcslen_0(L"rehydrate-pending-to-hot");
  v85 = (const wchar_t *)v83;
  if ( *(_QWORD *)(v83 + 24) > 7u )
    v85 = *(const wchar_t **)v83;
  v86 = (size_t *)(v83 + 16);
  v87 = *(_QWORD *)(v83 + 16);
  if ( v87 != v84 || v87 && wmemcmp(v85, L"rehydrate-pending-to-hot", v87) )
  {
    v88 = wcslen_0(L"rehydrate-pending-to-cool");
    if ( *(_QWORD *)(v83 + 24) > 7u )
      v83 = *(_QWORD *)v83;
    v89 = *v86;
    if ( *v86 == v88 && (!v89 || !wmemcmp((const wchar_t *)v83, L"rehydrate-pending-to-cool", v89)) )
      v4 = 2;
    else
      v4 = 0;
  }
  *(_DWORD *)(a1 + 336) = v4;
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v90 = Block[0];
    }
    else
    {
      v90 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v90 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v90);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
  {
    if ( 2 * v118 + 2 < 0x1000 )
    {
      v91 = pExceptionObject[0];
    }
    else
    {
      v91 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
      if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v91 - 8) > 0x1F )
        goto LABEL_254;
    }
    operator delete(v91);
  }
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v92 = wcslen_0(L"x-ms-server-encrypted");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-server-encrypted", v92);
  v93 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  *(_BYTE *)(a1 + 356) = azure::storage::protocol::response_parsers::parse_boolean(v93);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v94 = Block[0];
    }
    else
    {
      v94 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v94 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v94);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
  {
    if ( 2 * v118 + 2 < 0x1000 )
    {
      v95 = pExceptionObject[0];
    }
    else
    {
      v95 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
      if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v95 - 8) > 0x1F )
        goto LABEL_254;
    }
    operator delete(v95);
  }
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v96 = wcslen_0(L"x-ms-incremental-copy");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-incremental-copy", v96);
  v97 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  *(_BYTE *)(a1 + 357) = azure::storage::protocol::response_parsers::parse_boolean(v97);
  if ( v115 > 7 )
  {
    if ( 2 * v115 + 2 < 0x1000 )
    {
      v98 = Block[0];
    }
    else
    {
      v98 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v98 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v98);
  }
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
  {
    if ( 2 * v118 + 2 < 0x1000 )
    {
      v99 = pExceptionObject[0];
    }
    else
    {
      v99 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
      if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v99 - 8) > 0x1F )
LABEL_254:
        __fastfail(5u);
    }
    operator delete(v99);
  }
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v100 = wcslen_0(L"x-ms-access-tier-inferred");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-access-tier-inferred", v100);
  v101 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  *(_BYTE *)(a1 + 358) = azure::storage::protocol::response_parsers::parse_boolean(v101);
  if ( v115 > 7 )
    std::wstring::_Deallocate_for_capacity(Block, Block[0]);
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
    std::wstring::_Deallocate_for_capacity(pExceptionObject, pExceptionObject[0]);
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v102 = wcslen_0(L"x-ms-encryption-key-sha256");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-encryption-key-sha256", v102);
  v103 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  std::wstring::operator=(a1 + 232, v103);
  if ( v115 > 7 )
    std::wstring::_Deallocate_for_capacity(Block, Block[0]);
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
    std::wstring::_Deallocate_for_capacity(pExceptionObject, pExceptionObject[0]);
  *(_OWORD *)pExceptionObject = 0;
  v117 = 0;
  v118 = 0;
  v104 = wcslen_0(L"x-ms-version-id");
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"x-ms-version-id", v104);
  v105 = azure::storage::protocol::get_header_value(Block, v7, pExceptionObject);
  std::wstring::operator=(a1 + 280, v105);
  if ( v115 > 7 )
    std::wstring::_Deallocate_for_capacity(Block, Block[0]);
  v114 = 0;
  v115 = 7;
  LOWORD(Block[0]) = 0;
  if ( v118 > 7 )
    std::wstring::_Deallocate_for_capacity(pExceptionObject, pExceptionObject[0]);
  if ( v121 > 7 )
    std::wstring::_Deallocate_for_capacity(S1, S1[0]);
  N = 0;
  v121 = 7;
  LOWORD(S1[0]) = 0;
  if ( v125[3] > 7u )
    std::wstring::_Deallocate_for_capacity(v125, v125[0]);
  return a1;
}

```

## disassembly

```asm
0x180099440  mov     [rsp-8+arg_10], rbx
0x180099445  push    rbp
0x180099446  push    rsi
0x180099447  push    rdi
0x180099448  push    r12
0x18009944a  push    r13
0x18009944c  push    r14
0x18009944e  push    r15
0x180099450  lea     rbp, [rsp-0D0h]
0x180099458  sub     rsp, 1D0h
0x18009945f  mov     rax, cs:__security_cookie
0x180099466  xor     rax, rsp
0x180099469  mov     [rbp+100h+var_38], rax
0x180099470  mov     rbx, rdx
0x180099473  mov     rdi, rcx
0x180099476  mov     [rbp+100h+var_E0], rcx
0x18009947a  xor     esi, esi
0x18009947c  mov     [rsp+200h+var_1E0], esi
0x180099480  call    ??0cloud_blob_properties@storage@azure@@QEAA@XZ; azure::storage::cloud_blob_properties::cloud_blob_properties(void)
0x180099485  mov     r12d, 1
0x18009948b  mov     [rsp+200h+var_1E0], r12d
0x180099490  mov     rdx, rbx
0x180099493  lea     rcx, [rbp+100h+Block]
0x180099497  call    ?parse_etag@protocol@storage@azure@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVhttp_response@http@web@@@Z; azure::storage::protocol::parse_etag(web::http::http_response const &)
0x18009949c  lea     rcx, [rdi+0C8h]
0x1800994a3  mov     rdx, rax
0x1800994a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800994ab  mov     rdx, [rbp+100h+var_C0]
0x1800994af  cmp     rdx, 7
0x1800994b3  jbe     short loc_1800994ED
0x1800994b5  mov     rax, [rbp+100h+Block]
0x1800994b9  lea     rdx, ds:2[rdx*2]
0x1800994c1  cmp     rdx, 1000h
0x1800994c8  jb      short loc_1800994E5
0x1800994ca  mov     rcx, [rax-8]
0x1800994ce  sub     rax, rcx
0x1800994d1  sub     rax, 8
0x1800994d5  cmp     rax, 1Fh
0x1800994d9  ja      loc_180099ECB
0x1800994df  add     rdx, 27h ; '''
0x1800994e3  jmp     short loc_1800994E8
0x1800994e5  mov     rcx, rax; Block
0x1800994e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800994ed  mov     rdx, rbx
0x1800994f0  lea     rcx, [rsp+200h+var_1D8]
0x1800994f5  call    ?parse_last_modified@protocol@storage@azure@@YA?AVdatetime@utility@@AEBVhttp_response@http@web@@@Z; azure::storage::protocol::parse_last_modified(web::http::http_response const &)
0x1800994fa  mov     rcx, [rax]
0x1800994fd  mov     [rdi+108h], rcx
0x180099504  mov     rcx, rbx
0x180099507  call    ?parse_lease_status@protocol@storage@azure@@YA?AW4lease_status@23@AEBVhttp_response@http@web@@@Z; azure::storage::protocol::parse_lease_status(web::http::http_response const &)
0x18009950c  mov     [rdi+13Ch], eax
0x180099512  mov     rcx, rbx
0x180099515  call    ?parse_lease_state@protocol@storage@azure@@YA?AW4lease_state@23@AEBVhttp_response@http@web@@@Z; azure::storage::protocol::parse_lease_state(web::http::http_response const &)
0x18009951a  mov     [rdi+140h], eax
0x180099520  mov     rcx, rbx
0x180099523  call    ?parse_lease_duration@protocol@storage@azure@@YA?AW4lease_duration@23@AEBVhttp_response@http@web@@@Z; azure::storage::protocol::parse_lease_duration(web::http::http_response const &)
0x180099528  mov     [rdi+144h], eax
0x18009952e  mov     rcx, rbx; struct web::http::http_response *
0x180099531  call    ?parse_blob_size@blob_response_parsers@protocol@storage@azure@@SA_KAEBVhttp_response@http@web@@@Z; azure::storage::protocol::blob_response_parsers::parse_blob_size(web::http::http_response const &)
0x180099536  mov     [rdi+80h], rax
0x18009953d  mov     r15, [rbx]
0x180099540  add     r15, 58h ; 'X'
0x180099544  xorps   xmm0, xmm0
0x180099547  movups  xmmword ptr [rbp+100h+var_78], xmm0
0x18009954e  mov     [rbp+100h+var_68], rsi
0x180099555  mov     [rbp+100h+var_60], rsi
0x18009955c  lea     rcx, ?ms_header_blob_sequence_number@protocol@storage@azure@@3QBGB; "x-ms-blob-sequence-number"
0x180099563  call    wcslen_0
0x180099568  mov     r8, rax
0x18009956b  lea     rdx, ?ms_header_blob_sequence_number@protocol@storage@azure@@3QBGB; "x-ms-blob-sequence-number"
0x180099572  lea     rcx, [rbp+100h+var_78]
0x180099579  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009957e  nop
0x18009957f  lea     r8, [rbp+100h+var_78]
0x180099586  mov     rdx, r15
0x180099589  lea     rcx, [rbp+100h+Block]
0x18009958d  call    ?get_header_value@protocol@storage@azure@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVhttp_headers@http@web@@AEBV45@@Z; azure::storage::protocol::get_header_value(web::http::http_headers const &,std::wstring const &)
0x180099592  mov     rbx, rax
0x180099595  lea     r13, ??_8?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B@; const std::basic_istringstream<ushort>::`vbtable'
0x18009959c  mov     [rsp+200h+var_1D0], r13
0x1800995a1  lea     rcx, [rbp+100h+var_140]
0x1800995a5  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x1800995ab  nop
0x1800995ac  mov     [rsp+200h+var_1E0], 5
0x1800995b4  xor     r9d, r9d
0x1800995b7  xor     r8d, r8d
0x1800995ba  lea     rdx, [rsp+200h+var_1C0]
0x1800995bf  lea     rcx, [rsp+200h+var_1D0]
0x1800995c4  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x1800995ca  nop
0x1800995cb  mov     rax, [rsp+200h+var_1D0]
0x1800995d0  movsxd  rcx, dword ptr [rax+4]
0x1800995d4  lea     r14, ??_7?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_istringstream<ushort>::`vftable'
0x1800995db  mov     [rsp+rcx+200h+var_1D0], r14
0x1800995e0  mov     rax, [rsp+200h+var_1D0]
0x1800995e5  movsxd  rcx, dword ptr [rax+4]
0x1800995e9  lea     edx, [rcx-90h]
0x1800995ef  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x1800995f3  mov     r8d, r12d
0x1800995f6  mov     rdx, rbx
0x1800995f9  lea     rcx, [rsp+200h+var_1C0]
0x1800995fe  call    ??0?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringbuf<ushort>::basic_stringbuf<ushort>(std::wstring const &,int)
0x180099603  nop
0x180099604  mov     rax, [rsp+200h+var_1D0]
0x180099609  movsxd  rcx, dword ptr [rax+4]
0x18009960d  lea     rbx, [rsp+200h+var_1D0]
0x180099612  add     rbx, rcx
0x180099615  call    ?classic@locale@std@@SAAEBV12@XZ_0; std::locale::classic(void)
0x18009961a  mov     r8, rax
0x18009961d  lea     rdx, [rbp+100h+pExceptionObject]
0x180099621  mov     rcx, rbx
0x180099624  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18009962a  mov     rcx, [rbp+100h+pExceptionObject+8]
0x18009962e  test    rcx, rcx
0x180099631  jz      short loc_180099655
0x180099633  mov     rax, [rcx]
0x180099636  mov     rax, [rax+10h]
0x18009963a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009963f  mov     rcx, rax
0x180099642  test    rax, rax
0x180099645  jz      short loc_180099655
0x180099647  mov     rax, [rax]
0x18009964a  mov     edx, r12d
0x18009964d  mov     rax, [rax]
0x180099650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099655  lea     rdx, [rsp+200h+var_1D8]
0x18009965a  lea     rcx, [rsp+200h+var_1D0]
0x18009965f  call    cs:__imp_??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z; std::basic_istream<ushort>::operator>>(__int64 &)
0x180099665  mov     rax, [rsp+200h+var_1D0]
0x18009966a  movsxd  rcx, dword ptr [rax+4]
0x18009966e  lea     rax, [rsp+200h+var_1D0]
0x180099673  add     rcx, rax
0x180099676  call    cs:__imp_?bad@ios_base@std@@QEBA_NXZ; std::ios_base::bad(void)
0x18009967c  test    al, al
0x18009967e  jnz     loc_18009A92F
0x180099684  mov     rbx, [rsp+200h+var_1D8]
0x180099689  mov     rax, [rsp+200h+var_1D0]
0x18009968e  movsxd  rcx, dword ptr [rax+4]
0x180099692  mov     [rsp+rcx+200h+var_1D0], r14
0x180099697  mov     rax, [rsp+200h+var_1D0]
0x18009969c  movsxd  rcx, dword ptr [rax+4]
0x1800996a0  lea     edx, [rcx-90h]
0x1800996a6  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x1800996aa  lea     rcx, [rsp+200h+var_1C0]
0x1800996af  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800996b4  lea     rcx, [rsp+200h+var_1B8]
0x1800996b9  call    cs:__imp_??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_istream<ushort>::~basic_istream<ushort,std::char_traits<ushort>>(void)
0x1800996bf  lea     rcx, [rbp+100h+var_140]
0x1800996c3  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800996c9  mov     [rdi+158h], rbx
0x1800996d0  mov     rdx, [rbp+100h+var_C0]
0x1800996d4  cmp     rdx, 7
0x1800996d8  jbe     short loc_180099715
0x1800996da  mov     rax, [rbp+100h+Block]
0x1800996de  lea     rdx, ds:2[rdx*2]
0x1800996e6  cmp     rdx, 1000h
0x1800996ed  jb      short loc_18009970D
0x1800996ef  mov     rcx, [rax-8]
0x1800996f3  sub     rax, rcx
0x1800996f6  sub     rax, 8
0x1800996fa  cmp     rax, 1Fh
0x1800996fe  ja      short loc_180099706
0x180099700  add     rdx, 27h ; '''
0x180099704  jmp     short loc_180099710
0x180099706  mov     ecx, 5
0x18009970b  int     29h; Win8: RtlFailFast(ecx)
0x18009970d  mov     rcx, rax; Block
0x180099710  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180099715  mov     [rbp+100h+var_C8], rsi
0x180099719  mov     [rbp+100h+var_C0], 7
0x180099721  mov     word ptr [rbp+100h+Block], si
0x180099725  mov     rdx, [rbp+100h+var_60]
0x18009972c  cmp     rdx, 7
0x180099730  jbe     short loc_18009976D
0x180099732  mov     rax, [rbp+100h+var_78]
0x180099739  lea     rdx, ds:2[rdx*2]
0x180099741  cmp     rdx, 1000h
0x180099748  jb      short loc_180099765
0x18009974a  mov     rcx, [rax-8]
0x18009974e  sub     rax, rcx
0x180099751  sub     rax, 8
0x180099755  cmp     rax, 1Fh
0x180099759  ja      loc_180099ECB
0x18009975f  add     rdx, 27h ; '''
0x180099763  jmp     short loc_180099768
0x180099765  mov     rcx, rax; Block
0x180099768  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009976d  xorps   xmm0, xmm0
0x180099770  movups  xmmword ptr [rbp+100h+var_78], xmm0
0x180099777  mov     [rbp+100h+var_68], rsi
0x18009977e  mov     [rbp+100h+var_60], rsi
0x180099785  lea     rcx, ?ms_header_blob_committed_block_count@protocol@storage@azure@@3QBGB; "x-ms-blob-committed-block-count"
0x18009978c  call    wcslen_0
0x180099791  mov     r8, rax
0x180099794  lea     rdx, ?ms_header_blob_committed_block_count@protocol@storage@azure@@3QBGB; "x-ms-blob-committed-block-count"
0x18009979b  lea     rcx, [rbp+100h+var_78]
0x1800997a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800997a7  nop
0x1800997a8  lea     r8, [rbp+100h+var_78]
0x1800997af  mov     rdx, r15
0x1800997b2  lea     rcx, [rbp+100h+Block]
0x1800997b6  call    ?get_header_value@protocol@storage@azure@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVhttp_headers@http@web@@AEBV45@@Z; azure::storage::protocol::get_header_value(web::http::http_headers const &,std::wstring const &)
0x1800997bb  mov     rbx, rax
0x1800997be  mov     [rsp+200h+var_1D0], r13
0x1800997c3  lea     rcx, [rbp+100h+var_140]
0x1800997c7  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x1800997cd  nop
0x1800997ce  mov     r13d, 0Dh
0x1800997d4  mov     [rsp+200h+var_1E0], r13d
0x1800997d9  xor     r9d, r9d
0x1800997dc  xor     r8d, r8d
0x1800997df  lea     rdx, [rsp+200h+var_1C0]
0x1800997e4  lea     rcx, [rsp+200h+var_1D0]
0x1800997e9  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x1800997ef  nop
0x1800997f0  mov     rax, [rsp+200h+var_1D0]
0x1800997f5  movsxd  rcx, dword ptr [rax+4]
0x1800997f9  mov     [rsp+rcx+200h+var_1D0], r14
0x1800997fe  mov     rax, [rsp+200h+var_1D0]
0x180099803  movsxd  rcx, dword ptr [rax+4]
0x180099807  lea     edx, [rcx-90h]
0x18009980d  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x180099811  mov     r8d, r12d
0x180099814  mov     rdx, rbx
0x180099817  lea     rcx, [rsp+200h+var_1C0]
0x18009981c  call    ??0?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringbuf<ushort>::basic_stringbuf<ushort>(std::wstring const &,int)
0x180099821  nop
0x180099822  mov     rax, [rsp+200h+var_1D0]
0x180099827  movsxd  rcx, dword ptr [rax+4]
0x18009982b  lea     rbx, [rsp+200h+var_1D0]
0x180099830  add     rbx, rcx
0x180099833  call    ?classic@locale@std@@SAAEBV12@XZ_0; std::locale::classic(void)
0x180099838  mov     r8, rax
0x18009983b  lea     rdx, [rbp+100h+pExceptionObject]
0x18009983f  mov     rcx, rbx
0x180099842  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x180099848  mov     rcx, [rbp+100h+pExceptionObject+8]
0x18009984c  test    rcx, rcx
0x18009984f  jz      short loc_180099873
0x180099851  mov     rax, [rcx]
0x180099854  mov     rax, [rax+10h]
0x180099858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009985d  mov     rcx, rax
0x180099860  test    rax, rax
0x180099863  jz      short loc_180099873
0x180099865  mov     rax, [rax]
0x180099868  mov     edx, r12d
0x18009986b  mov     rax, [rax]
0x18009986e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099873  lea     rdx, [rsp+200h+var_1D8]
0x180099878  lea     rcx, [rsp+200h+var_1D0]
0x18009987d  call    cs:__imp_??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAH@Z; std::basic_istream<ushort>::operator>>(int &)
0x180099883  mov     rax, [rsp+200h+var_1D0]
0x180099888  movsxd  rcx, dword ptr [rax+4]
0x18009988c  lea     rax, [rsp+200h+var_1D0]
0x180099891  add     rcx, rax
0x180099894  call    cs:__imp_?bad@ios_base@std@@QEBA_NXZ; std::ios_base::bad(void)
0x18009989a  test    al, al
0x18009989c  jnz     loc_18009A915
0x1800998a2  mov     ebx, dword ptr [rsp+200h+var_1D8]
0x1800998a6  mov     rax, [rsp+200h+var_1D0]
0x1800998ab  movsxd  rcx, dword ptr [rax+4]
0x1800998af  mov     [rsp+rcx+200h+var_1D0], r14
0x1800998b4  mov     rax, [rsp+200h+var_1D0]
0x1800998b9  movsxd  rcx, dword ptr [rax+4]
0x1800998bd  lea     edx, [rcx-90h]
0x1800998c3  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x1800998c7  lea     rcx, [rsp+200h+var_1C0]
0x1800998cc  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800998d1  lea     rcx, [rsp+200h+var_1B8]
0x1800998d6  call    cs:__imp_??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_istream<ushort>::~basic_istream<ushort,std::char_traits<ushort>>(void)
0x1800998dc  lea     rcx, [rbp+100h+var_140]
0x1800998e0  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800998e6  mov     [rdi+160h], ebx
0x1800998ec  mov     rdx, [rbp+100h+var_C0]
0x1800998f0  cmp     rdx, 7
0x1800998f4  jbe     short loc_180099931
0x1800998f6  mov     rax, [rbp+100h+Block]
0x1800998fa  lea     rdx, ds:2[rdx*2]
0x180099902  cmp     rdx, 1000h
0x180099909  jb      short loc_180099929
0x18009990b  mov     rcx, [rax-8]
0x18009990f  sub     rax, rcx
0x180099912  sub     rax, 8
0x180099916  cmp     rax, 1Fh
0x18009991a  ja      short loc_180099922
0x18009991c  add     rdx, 27h ; '''
0x180099920  jmp     short loc_18009992C
0x180099922  mov     ecx, 5
0x180099927  int     29h; Win8: RtlFailFast(ecx)
0x180099929  mov     rcx, rax; Block
0x18009992c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180099931  mov     [rbp+100h+var_C8], rsi
0x180099935  mov     [rbp+100h+var_C0], 7
0x18009993d  mov     word ptr [rbp+100h+Block], si
0x180099941  mov     rdx, [rbp+100h+var_60]
0x180099948  cmp     rdx, 7
0x18009994c  jbe     short loc_180099989
0x18009994e  mov     rax, [rbp+100h+var_78]
0x180099955  lea     rdx, ds:2[rdx*2]
  ... truncated ...
```
