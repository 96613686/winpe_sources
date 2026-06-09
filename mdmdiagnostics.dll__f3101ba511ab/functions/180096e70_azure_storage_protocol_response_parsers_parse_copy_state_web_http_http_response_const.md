# azure::storage::protocol::response_parsers::parse_copy_state(web::http::http_response const &)

- ea: `0x180096e70`
- end: `0x180097ba5`
- name: `?parse_copy_state@response_parsers@protocol@storage@azure@@SA?AVcopy_state@34@AEBVhttp_response@http@web@@@Z`
- size: `3381`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180073710`

## callees

- `0x180019080`
- `0x180019588`
- `0x180020f50`
- `0x180021fa0`
- `0x180072c40`
- `0x180095140`
- `0x180096cd0`
- `0x180096e70`
- `0x1800aa020`
- `0x1800e53ec`
- `0x1800e54e0`
- `0x1800e7be0`
- `0x1800eeef0`
- `0x1800f7a78`
- `0x1800fa7d4`
- `0x1801089a8`

## import_xrefs

- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097abf`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097abf`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x180097a1e`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x180097a1e`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097ac9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097ac9`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x180097a6e`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x180097a88`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x180097a6e`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x180097a88`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800979ff`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800979ff`

## string_xrefs

- `0x1800970c6`: `x-ms-copy-id`
- `0x1800970d5`: `x-ms-copy-id`
- `0x1800973e6`: `x-ms-copy-completion-time`
- `0x1800973f5`: `x-ms-copy-completion-time`
- `0x180096edd`: `x-ms-copy-status`
- `0x180096eec`: `x-ms-copy-status`
- `0x180097909`: `x-ms-copy-progress`
- `0x180097918`: `x-ms-copy-progress`
- `0x1800975a1`: `x-ms-copy-status-description`
- `0x1800975b0`: `x-ms-copy-status-description`
- `0x180097255`: `x-ms-copy-source`
- `0x180097264`: `x-ms-copy-source`
- `0x180097736`: `x-ms-copy-destination-snapshot`
- `0x180097745`: `x-ms-copy-destination-snapshot`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall azure::storage::protocol::response_parsers::parse_copy_state(__int64 a1, __int64 *a2)
{
  __int64 v4; // rsi
  size_t v5; // rax
  void *v6; // rcx
  size_t v7; // rbx
  size_t v8; // rax
  unsigned __int64 v9; // rdi
  const wchar_t *v10; // rcx
  wchar_t *v11; // r14
  size_t v12; // rax
  wchar_t **v13; // rcx
  size_t v14; // rax
  wchar_t **v15; // rcx
  size_t v16; // rax
  wchar_t **v17; // rcx
  int v18; // eax
  size_t v19; // rax
  __int64 *v20; // rdi
  __int64 *v21; // rbx
  __int64 *v22; // rax
  __int64 *v23; // rdx
  void *v24; // rcx
  void *v25; // rcx
  size_t v26; // rax
  __int64 *v27; // rdi
  __int64 *v28; // rbx
  __int64 *v29; // rax
  __int64 *v30; // rdx
  void *v31; // rcx
  void *v32; // rcx
  size_t v33; // rax
  __int64 *v34; // rdi
  __int64 *v35; // rbx
  __int64 *v36; // rax
  __int64 *v37; // rdx
  __int64 v38; // rax
  void *v39; // rcx
  void *v40; // rcx
  size_t v41; // rax
  __int64 *v42; // rdi
  __int64 *v43; // rbx
  __int64 *v44; // rax
  __int64 *v45; // rdx
  void *v46; // rcx
  void *v47; // rcx
  size_t v48; // rax
  __int64 *v49; // rdi
  __int64 *v50; // rbx
  __int64 *v51; // rax
  __int64 *v52; // rdx
  __int64 v53; // rax
  void *v54; // rcx
  void *v55; // rcx
  size_t v56; // rax
  __int64 v57; // r14
  __int64 *v58; // rdi
  __int64 *v59; // rbx
  __int64 *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  void *v63; // rcx
  wchar_t *v64; // rcx
  __int64 v66; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v67[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v68; // [rsp+38h] [rbp-C8h]
  _QWORD v69[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v70[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v71[120]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v72[96]; // [rsp+D0h] [rbp-30h] BYREF
  void *v73[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v74; // [rsp+140h] [rbp+40h]
  unsigned __int64 v75; // [rsp+148h] [rbp+48h]
  wchar_t *S1[2]; // [rsp+150h] [rbp+50h] BYREF
  size_t N; // [rsp+160h] [rbp+60h]
  unsigned __int64 v78; // [rsp+168h] [rbp+68h]
  void *v79[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v80; // [rsp+180h] [rbp+80h]
  unsigned __int64 v81; // [rsp+188h] [rbp+88h]
  void *v82[2]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v83; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v84; // [rsp+1A8h] [rbp+A8h]
  void *Block[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v86; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v87; // [rsp+1C8h] [rbp+C8h]
  void *v88[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v89; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v90; // [rsp+1E8h] [rbp+E8h]
  void *v91[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v92; // [rsp+200h] [rbp+100h]
  unsigned __int64 v93; // [rsp+208h] [rbp+108h]
  void *v94[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v95; // [rsp+220h] [rbp+120h]
  unsigned __int64 v96; // [rsp+228h] [rbp+128h]
  void *v97[2]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v98; // [rsp+240h] [rbp+140h]
  unsigned __int64 v99; // [rsp+248h] [rbp+148h]

  v68 = a1;
  azure::storage::copy_state::copy_state((azure::storage::copy_state *)a1);
  v4 = *a2;
  *(_OWORD *)Block = 0;
  v86 = 0;
  v87 = 0;
  v5 = wcslen_0(L"x-ms-copy-status");
  std::wstring::_Construct<1,unsigned short const *>(Block, L"x-ms-copy-status", v5);
  azure::storage::protocol::get_header_value(S1, v4 + 88, Block);
  if ( v87 > 7 )
  {
    if ( 2 * v87 + 2 < 0x1000 )
    {
      v6 = Block[0];
    }
    else
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        goto LABEL_184;
    }
    operator delete(v6);
  }
  v86 = 0;
  v87 = 7;
  LOWORD(Block[0]) = 0;
  v7 = N;
  if ( !N )
    goto LABEL_210;
  v8 = wcslen_0(L"pending");
  v9 = v78;
  v10 = (const wchar_t *)S1;
  v11 = S1[0];
  if ( v78 > 7 )
    v10 = S1[0];
  if ( v7 == v8 )
  {
    if ( !v7 || !wmemcmp(v10, L"pending", v7) )
    {
      v18 = 1;
      goto LABEL_36;
    }
    v9 = v78;
    v7 = N;
    v11 = S1[0];
  }
  v12 = wcslen_0(L"success");
  v13 = S1;
  if ( v9 > 7 )
    v13 = (wchar_t **)v11;
  if ( v7 == v12 )
  {
    if ( !v7 || !wmemcmp((const wchar_t *)v13, L"success", v7) )
    {
      v18 = 2;
      goto LABEL_36;
    }
    v9 = v78;
    v7 = N;
    v11 = S1[0];
  }
  v14 = wcslen_0(L"aborted");
  v15 = S1;
  if ( v9 > 7 )
    v15 = (wchar_t **)v11;
  if ( v7 != v14 )
    goto LABEL_26;
  if ( v7 && wmemcmp((const wchar_t *)v15, L"aborted", v7) )
  {
    v9 = v78;
    v7 = N;
    v11 = S1[0];
LABEL_26:
    v16 = wcslen_0(L"failed");
    v17 = S1;
    if ( v9 > 7 )
      v17 = (wchar_t **)v11;
    if ( v7 == v16 && (!v7 || !wmemcmp((const wchar_t *)v17, L"failed", v7)) )
      v18 = 4;
    else
      v18 = 0;
    goto LABEL_36;
  }
  v18 = 3;
LABEL_36:
  *(_DWORD *)(a1 + 88) = v18;
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v19 = wcslen_0(L"x-ms-copy-id");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-id", v19);
  *(_OWORD *)v91 = 0;
  v92 = 0;
  v93 = 7;
  LOWORD(v91[0]) = 0;
  v20 = *(__int64 **)(v4 + 88);
  v21 = (__int64 *)v20[1];
  if ( *((_BYTE *)v21 + 25) )
  {
    v22 = *(__int64 **)(v4 + 88);
  }
  else
  {
    do
    {
      if ( (unsigned __int8)utility::details::str_iless(v21 + 4, v73) )
      {
        v21 = (__int64 *)v21[2];
      }
      else
      {
        v20 = v21;
        v21 = (__int64 *)*v21;
      }
    }
    while ( !*((_BYTE *)v21 + 25) );
    v22 = *(__int64 **)(v4 + 88);
  }
  if ( *((_BYTE *)v20 + 25) )
  {
    v20 = v22;
  }
  else if ( (unsigned __int8)utility::details::str_iless(v73, v20 + 4) )
  {
    v20 = *(__int64 **)(v4 + 88);
  }
  if ( v20 != *(__int64 **)(v4 + 88) && v91 != (void **)(v20 + 8) )
  {
    if ( (unsigned __int64)v20[11] <= 7 )
      v23 = v20 + 8;
    else
      v23 = (__int64 *)v20[8];
    std::wstring::_Assign<unsigned short>(v91, v23, v20[10]);
  }
  std::wstring::operator=(a1, v91);
  if ( v93 > 7 )
  {
    if ( 2 * v93 + 2 < 0x1000 )
    {
      v24 = v91[0];
    }
    else
    {
      v24 = (void *)*((_QWORD *)v91[0] - 1);
      if ( (unsigned __int64)((char *)v91[0] - (char *)v24 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v24);
  }
  if ( v75 > 7 )
  {
    if ( 2 * v75 + 2 < 0x1000 )
    {
      v25 = v73[0];
    }
    else
    {
      v25 = (void *)*((_QWORD *)v73[0] - 1);
      if ( (unsigned __int64)((char *)v73[0] - (char *)v25 - 8) > 0x1F )
        goto LABEL_184;
    }
    operator delete(v25);
  }
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v26 = wcslen_0(L"x-ms-copy-source");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-source", v26);
  *(_OWORD *)v94 = 0;
  v95 = 0;
  v96 = 7;
  LOWORD(v94[0]) = 0;
  v27 = *(__int64 **)(v4 + 88);
  v28 = (__int64 *)v27[1];
  if ( *((_BYTE *)v28 + 25) )
  {
    v29 = *(__int64 **)(v4 + 88);
  }
  else
  {
    do
    {
      if ( (unsigned __int8)utility::details::str_iless(v28 + 4, v73) )
      {
        v28 = (__int64 *)v28[2];
      }
      else
      {
        v27 = v28;
        v28 = (__int64 *)*v28;
      }
    }
    while ( !*((_BYTE *)v28 + 25) );
    v29 = *(__int64 **)(v4 + 88);
  }
  if ( *((_BYTE *)v27 + 25) )
  {
    v27 = v29;
  }
  else if ( (unsigned __int8)utility::details::str_iless(v73, v27 + 4) )
  {
    v27 = *(__int64 **)(v4 + 88);
  }
  if ( v27 != *(__int64 **)(v4 + 88) && v94 != (void **)(v27 + 8) )
  {
    if ( (unsigned __int64)v27[11] <= 7 )
      v30 = v27 + 8;
    else
      v30 = (__int64 *)v27[8];
    std::wstring::_Assign<unsigned short>(v94, v30, v27[10]);
  }
  std::wstring::operator=(a1 + 96, v94);
  if ( v96 > 7 )
  {
    if ( 2 * v96 + 2 < 0x1000 )
    {
      v31 = v94[0];
    }
    else
    {
      v31 = (void *)*((_QWORD *)v94[0] - 1);
      if ( (unsigned __int64)((char *)v94[0] - (char *)v31 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v31);
  }
  if ( v75 > 7 )
  {
    if ( 2 * v75 + 2 < 0x1000 )
    {
      v32 = v73[0];
    }
    else
    {
      v32 = (void *)*((_QWORD *)v73[0] - 1);
      if ( (unsigned __int64)((char *)v73[0] - (char *)v32 - 8) > 0x1F )
        goto LABEL_184;
    }
    operator delete(v32);
  }
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v33 = wcslen_0(L"x-ms-copy-completion-time");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-completion-time", v33);
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 7;
  LOWORD(v79[0]) = 0;
  v34 = *(__int64 **)(v4 + 88);
  v35 = (__int64 *)v34[1];
  if ( *((_BYTE *)v35 + 25) )
  {
    v36 = *(__int64 **)(v4 + 88);
  }
  else
  {
    do
    {
      if ( (unsigned __int8)utility::details::str_iless(v35 + 4, v73) )
      {
        v35 = (__int64 *)v35[2];
      }
      else
      {
        v34 = v35;
        v35 = (__int64 *)*v35;
      }
    }
    while ( !*((_BYTE *)v35 + 25) );
    v36 = *(__int64 **)(v4 + 88);
  }
  if ( *((_BYTE *)v34 + 25) )
  {
    v34 = v36;
  }
  else if ( (unsigned __int8)utility::details::str_iless(v73, v34 + 4) )
  {
    v34 = *(__int64 **)(v4 + 88);
  }
  if ( v34 != *(__int64 **)(v4 + 88) && v79 != (void **)(v34 + 8) )
  {
    if ( (unsigned __int64)v34[11] <= 7 )
      v37 = v34 + 8;
    else
      v37 = (__int64 *)v34[8];
    std::wstring::_Assign<unsigned short>(v79, v37, v34[10]);
  }
  if ( v80 )
  {
    utility::datetime::from_string(&v66, v79, 0);
    v38 = v66;
  }
  else
  {
    v66 = 0;
    v38 = 0;
  }
  *(_QWORD *)(a1 + 32) = v38;
  if ( v81 > 7 )
  {
    if ( 2 * v81 + 2 < 0x1000 )
    {
      v39 = v79[0];
    }
    else
    {
      v39 = (void *)*((_QWORD *)v79[0] - 1);
      if ( (unsigned __int64)((char *)v79[0] - (char *)v39 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v39);
  }
  v80 = 0;
  v81 = 7;
  LOWORD(v79[0]) = 0;
  if ( v75 > 7 )
  {
    if ( 2 * v75 + 2 < 0x1000 )
    {
      v40 = v73[0];
    }
    else
    {
      v40 = (void *)*((_QWORD *)v73[0] - 1);
      if ( (unsigned __int64)((char *)v73[0] - (char *)v40 - 8) > 0x1F )
        goto LABEL_184;
    }
    operator delete(v40);
  }
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v41 = wcslen_0(L"x-ms-copy-status-description");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-status-description", v41);
  *(_OWORD *)v97 = 0;
  v98 = 0;
  v99 = 7;
  LOWORD(v97[0]) = 0;
  v42 = *(__int64 **)(v4 + 88);
  v43 = (__int64 *)v42[1];
  if ( *((_BYTE *)v43 + 25) )
  {
    v44 = *(__int64 **)(v4 + 88);
  }
  else
  {
    do
    {
      if ( (unsigned __int8)utility::details::str_iless(v43 + 4, v73) )
      {
        v43 = (__int64 *)v43[2];
      }
      else
      {
        v42 = v43;
        v43 = (__int64 *)*v43;
      }
    }
    while ( !*((_BYTE *)v43 + 25) );
    v44 = *(__int64 **)(v4 + 88);
  }
  if ( *((_BYTE *)v42 + 25) )
  {
    v42 = v44;
  }
  else if ( (unsigned __int8)utility::details::str_iless(v73, v42 + 4) )
  {
    v42 = *(__int64 **)(v4 + 88);
  }
  if ( v42 != *(__int64 **)(v4 + 88) && v97 != (void **)(v42 + 8) )
  {
    if ( (unsigned __int64)v42[11] <= 7 )
      v45 = v42 + 8;
    else
      v45 = (__int64 *)v42[8];
    std::wstring::_Assign<unsigned short>(v97, v45, v42[10]);
  }
  std::wstring::operator=(a1 + 40, v97);
  if ( v99 > 7 )
  {
    if ( 2 * v99 + 2 < 0x1000 )
    {
      v46 = v97[0];
    }
    else
    {
      v46 = (void *)*((_QWORD *)v97[0] - 1);
      if ( (unsigned __int64)((char *)v97[0] - (char *)v46 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v46);
  }
  if ( v75 > 7 )
  {
    if ( 2 * v75 + 2 < 0x1000 )
    {
      v47 = v73[0];
    }
    else
    {
      v47 = (void *)*((_QWORD *)v73[0] - 1);
      if ( (unsigned __int64)((char *)v73[0] - (char *)v47 - 8) > 0x1F )
        goto LABEL_184;
    }
    operator delete(v47);
  }
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v48 = wcslen_0(L"x-ms-copy-destination-snapshot");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-destination-snapshot", v48);
  *(_OWORD *)v82 = 0;
  v83 = 0;
  v84 = 7;
  LOWORD(v82[0]) = 0;
  v49 = *(__int64 **)(v4 + 88);
  v50 = (__int64 *)v49[1];
  if ( *((_BYTE *)v50 + 25) )
  {
    v51 = *(__int64 **)(v4 + 88);
  }
  else
  {
    do
    {
      if ( (unsigned __int8)utility::details::str_iless(v50 + 4, v73) )
      {
        v50 = (__int64 *)v50[2];
      }
      else
      {
        v49 = v50;
        v50 = (__int64 *)*v50;
      }
    }
    while ( !*((_BYTE *)v50 + 25) );
    v51 = *(__int64 **)(v4 + 88);
  }
  if ( *((_BYTE *)v49 + 25) )
  {
    v49 = v51;
  }
  else if ( (unsigned __int8)utility::details::str_iless(v73, v49 + 4) )
  {
    v49 = *(__int64 **)(v4 + 88);
  }
  if ( v49 != *(__int64 **)(v4 + 88) && v82 != (void **)(v49 + 8) )
  {
    if ( (unsigned __int64)v49[11] <= 7 )
      v52 = v49 + 8;
    else
      v52 = (__int64 *)v49[8];
    std::wstring::_Assign<unsigned short>(v82, v52, v49[10]);
  }
  if ( v83 )
  {
    utility::datetime::from_string(&v66, v82, 1);
    v53 = v66;
  }
  else
  {
    v66 = 0;
    v53 = 0;
  }
  *(_QWORD *)(a1 + 136) = v53;
  if ( v84 > 7 )
  {
    if ( 2 * v84 + 2 < 0x1000 )
    {
      v54 = v82[0];
    }
    else
    {
      v54 = (void *)*((_QWORD *)v82[0] - 1);
      if ( (unsigned __int64)((char *)v82[0] - (char *)v54 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v54);
  }
  v83 = 0;
  v84 = 7;
  LOWORD(v82[0]) = 0;
  if ( v75 > 7 )
  {
    if ( 2 * v75 + 2 < 0x1000 )
    {
      v55 = v73[0];
    }
    else
    {
      v55 = (void *)*((_QWORD *)v73[0] - 1);
      if ( (unsigned __int64)((char *)v73[0] - (char *)v55 - 8) > 0x1F )
LABEL_184:
        __fastfail(5u);
    }
    operator delete(v55);
  }
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  v56 = wcslen_0(L"x-ms-copy-progress");
  std::wstring::_Construct<1,unsigned short const *>(v73, L"x-ms-copy-progress", v56);
  *(_OWORD *)v88 = 0;
  v57 = 0;
  v89 = 0;
  v90 = 7;
  LOWORD(v88[0]) = 0;
  v58 = *(__int64 **)(v4 + 88);
  v59 = (__int64 *)v58[1];
  while ( !*((_BYTE *)v59 + 25) )
  {
    if ( (unsigned __int8)utility::details::str_iless(v59 + 4, v73) )
    {
      v59 = (__int64 *)v59[2];
    }
    else
    {
      v58 = v59;
      v59 = (__int64 *)*v59;
    }
  }
  if ( !*((_BYTE *)v58 + 25)
    && !(unsigned __int8)utility::details::str_iless(v73, v58 + 4)
    && v58 != *(__int64 **)(v4 + 88)
    && v88 != (void **)(v58 + 8) )
  {
    if ( (unsigned __int64)v58[11] <= 7 )
      v60 = v58 + 8;
    else
      v60 = (__int64 *)v58[8];
    std::wstring::_Assign<unsigned short>(v88, v60, v58[10]);
    v57 = v89;
  }
  if ( v57 )
  {
    v69[0] = &std::basic_istringstream<unsigned short>::`vbtable';
    std::basic_ios<unsigned short>::basic_ios<unsigned short>(v72);
    std::basic_istream<unsigned short>::basic_istream<unsigned short>(v69, v70, 0, 0, 385);
    *(_QWORD *)((char *)v69 + *(int *)(v69[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
    *(_DWORD *)((char *)&v68 + *(int *)(v69[0] + 4LL) + 4) = *(_DWORD *)(v69[0] + 4LL) - 144;
    std::basic_stringbuf<unsigned short>::basic_stringbuf<unsigned short>(v70, v88, 1);
    v61 = std::basic_istream<unsigned short>::operator>>(v69, a1 + 72);
    v62 = std::operator>><unsigned short,std::char_traits<unsigned short>>(v61, v67);
    std::basic_istream<unsigned short>::operator>>(v62, a1 + 80);
    *(_QWORD *)((char *)v69 + *(int *)(v69[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
    *(_DWORD *)((char *)&v68 + *(int *)(v69[0] + 4LL) + 4) = *(_DWORD *)(v69[0] + 4LL) - 144;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v70);
    std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(v71);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v72);
  }
  if ( v90 > 7 )
  {
    if ( 2 * v90 + 2 < 0x1000 )
    {
      v63 = v88[0];
    }
    else
    {
      v63 = (void *)*((_QWORD *)v88[0] - 1);
      if ( (unsigned __int64)((char *)v88[0] - (char *)v63 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v63);
  }
  if ( v75 > 7 )
    std::wstring::_Deallocate_for_capacity(v73, v73[0]);
LABEL_210:
  if ( v78 > 7 )
  {
    v64 = S1[0];
    if ( 2 * v78 + 2 >= 0x1000 )
    {
      if ( (unsigned __int64)S1[0] - *((_QWORD *)S1[0] - 1) - 8 > 0x1F )
        __fastfail(5u);
      v64 = (wchar_t *)*((_QWORD *)S1[0] - 1);
    }
    operator delete(v64);
  }
  return a1;
}

```

## disassembly

```asm
0x180096e70  mov     [rsp-8+arg_10], rbx
0x180096e75  mov     [rsp-8+arg_18], rsi
0x180096e7a  push    rbp
0x180096e7b  push    rdi
0x180096e7c  push    r12
0x180096e7e  push    r14
0x180096e80  push    r15
0x180096e82  lea     rbp, [rsp-160h]
0x180096e8a  sub     rsp, 260h
0x180096e91  mov     rax, cs:__security_cookie
0x180096e98  xor     rax, rsp
0x180096e9b  mov     [rbp+180h+var_30], rax
0x180096ea2  mov     rbx, rdx
0x180096ea5  mov     r15, rcx
0x180096ea8  mov     [rsp+280h+var_248], rcx
0x180096ead  xor     r12d, r12d
0x180096eb0  mov     [rsp+280h+var_260], r12d
0x180096eb5  call    ??0copy_state@storage@azure@@QEAA@XZ; azure::storage::copy_state::copy_state(void)
0x180096eba  mov     [rsp+280h+var_260], 1
0x180096ec2  mov     rsi, [rbx]
0x180096ec5  xorps   xmm0, xmm0
0x180096ec8  movups  xmmword ptr [rbp+180h+Block], xmm0
0x180096ecf  mov     [rbp+180h+var_C0], r12
0x180096ed6  mov     [rbp+180h+var_B8], r12
0x180096edd  lea     rcx, ?ms_header_copy_status@protocol@storage@azure@@3QBGB; "x-ms-copy-status"
0x180096ee4  call    wcslen_0
0x180096ee9  mov     r8, rax
0x180096eec  lea     rdx, ?ms_header_copy_status@protocol@storage@azure@@3QBGB; "x-ms-copy-status"
0x180096ef3  lea     rcx, [rbp+180h+Block]
0x180096efa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180096eff  nop
0x180096f00  lea     r8, [rbp+180h+Block]
0x180096f07  lea     rdx, [rsi+58h]
0x180096f0b  lea     rcx, [rbp+180h+S1]
0x180096f0f  call    ?get_header_value@protocol@storage@azure@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVhttp_headers@http@web@@AEBV45@@Z; azure::storage::protocol::get_header_value(web::http::http_headers const &,std::wstring const &)
0x180096f14  nop
0x180096f15  mov     rdx, [rbp+180h+var_B8]
0x180096f1c  cmp     rdx, 7
0x180096f20  jbe     short loc_180096F5D
0x180096f22  mov     rax, [rbp+180h+Block]
0x180096f29  lea     rdx, ds:2[rdx*2]
0x180096f31  cmp     rdx, 1000h
0x180096f38  jb      short loc_180096F55
0x180096f3a  mov     rcx, [rax-8]
0x180096f3e  sub     rax, rcx
0x180096f41  sub     rax, 8
0x180096f45  cmp     rax, 1Fh
0x180096f49  ja      loc_1800978EB
0x180096f4f  add     rdx, 27h ; '''
0x180096f53  jmp     short loc_180096F58
0x180096f55  mov     rcx, rax; Block
0x180096f58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180096f5d  mov     [rbp+180h+var_C0], r12
0x180096f64  mov     [rbp+180h+var_B8], 7
0x180096f6f  mov     word ptr [rbp+180h+Block], r12w
0x180096f77  mov     rbx, [rbp+180h+N]
0x180096f7b  test    rbx, rbx
0x180096f7e  jz      loc_180097B34
0x180096f84  lea     rcx, ?header_value_copy_pending@protocol@storage@azure@@3QBGB; "pending"
0x180096f8b  call    wcslen_0
0x180096f90  mov     rdi, [rbp+180h+var_118]
0x180096f94  lea     rcx, [rbp+180h+S1]
0x180096f98  mov     r14, [rbp+180h+S1]
0x180096f9c  cmp     rdi, 7
0x180096fa0  cmova   rcx, r14; S1
0x180096fa4  cmp     rbx, rax
0x180096fa7  jnz     short loc_180096FD5
0x180096fa9  test    rbx, rbx
0x180096fac  jz      loc_18009709B
0x180096fb2  mov     r8, rbx; N
0x180096fb5  lea     rdx, ?header_value_copy_pending@protocol@storage@azure@@3QBGB; "pending"
0x180096fbc  call    wmemcmp
0x180096fc1  test    eax, eax
0x180096fc3  jz      loc_18009709B
0x180096fc9  mov     rdi, [rbp+180h+var_118]
0x180096fcd  mov     rbx, [rbp+180h+N]
0x180096fd1  mov     r14, [rbp+180h+S1]
0x180096fd5  lea     rcx, ?header_value_copy_success@protocol@storage@azure@@3QBGB; "success"
0x180096fdc  call    wcslen_0
0x180096fe1  lea     rcx, [rbp+180h+S1]
0x180096fe5  cmp     rdi, 7
0x180096fe9  cmova   rcx, r14; S1
0x180096fed  cmp     rbx, rax
0x180096ff0  jnz     short loc_18009701E
0x180096ff2  test    rbx, rbx
0x180096ff5  jz      loc_1800970A2
0x180096ffb  mov     r8, rbx; N
0x180096ffe  lea     rdx, ?header_value_copy_success@protocol@storage@azure@@3QBGB; "success"
0x180097005  call    wmemcmp
0x18009700a  test    eax, eax
0x18009700c  jz      loc_1800970A2
0x180097012  mov     rdi, [rbp+180h+var_118]
0x180097016  mov     rbx, [rbp+180h+N]
0x18009701a  mov     r14, [rbp+180h+S1]
0x18009701e  lea     rcx, ?header_value_copy_aborted@protocol@storage@azure@@3QBGB; "aborted"
0x180097025  call    wcslen_0
0x18009702a  lea     rcx, [rbp+180h+S1]
0x18009702e  cmp     rdi, 7
0x180097032  cmova   rcx, r14; S1
0x180097036  cmp     rbx, rax
0x180097039  jnz     short loc_18009705F
0x18009703b  test    rbx, rbx
0x18009703e  jz      short loc_1800970A9
0x180097040  mov     r8, rbx; N
0x180097043  lea     rdx, ?header_value_copy_aborted@protocol@storage@azure@@3QBGB; "aborted"
0x18009704a  call    wmemcmp
0x18009704f  test    eax, eax
0x180097051  jz      short loc_1800970A9
0x180097053  mov     rdi, [rbp+180h+var_118]
0x180097057  mov     rbx, [rbp+180h+N]
0x18009705b  mov     r14, [rbp+180h+S1]
0x18009705f  lea     rcx, ?header_value_copy_failed@protocol@storage@azure@@3QBGB; "failed"
0x180097066  call    wcslen_0
0x18009706b  lea     rcx, [rbp+180h+S1]
0x18009706f  cmp     rdi, 7
0x180097073  cmova   rcx, r14; S1
0x180097077  cmp     rbx, rax
0x18009707a  jnz     short loc_1800970B0
0x18009707c  test    rbx, rbx
0x18009707f  jz      short loc_180097094
0x180097081  mov     r8, rbx; N
0x180097084  lea     rdx, ?header_value_copy_failed@protocol@storage@azure@@3QBGB; "failed"
0x18009708b  call    wmemcmp
0x180097090  test    eax, eax
0x180097092  jnz     short loc_1800970B0
0x180097094  mov     eax, 4
0x180097099  jmp     short loc_1800970B3
0x18009709b  mov     eax, 1
0x1800970a0  jmp     short loc_1800970B3
0x1800970a2  mov     eax, 2
0x1800970a7  jmp     short loc_1800970B3
0x1800970a9  mov     eax, 3
0x1800970ae  jmp     short loc_1800970B3
0x1800970b0  mov     eax, r12d
0x1800970b3  mov     [r15+58h], eax
0x1800970b7  xorps   xmm0, xmm0
0x1800970ba  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x1800970be  mov     [rbp+180h+var_140], r12
0x1800970c2  mov     [rbp+180h+var_138], r12
0x1800970c6  lea     rcx, ?ms_header_copy_id@protocol@storage@azure@@3QBGB; "x-ms-copy-id"
0x1800970cd  call    wcslen_0
0x1800970d2  mov     r8, rax
0x1800970d5  lea     rdx, ?ms_header_copy_id@protocol@storage@azure@@3QBGB; "x-ms-copy-id"
0x1800970dc  lea     rcx, [rbp+180h+var_150]
0x1800970e0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800970e5  nop
0x1800970e6  xorps   xmm0, xmm0
0x1800970e9  movups  xmmword ptr [rbp+180h+var_90], xmm0
0x1800970f0  mov     [rbp+180h+var_80], r12
0x1800970f7  mov     [rbp+180h+var_78], 7
0x180097102  mov     word ptr [rbp+180h+var_90], r12w
0x18009710a  mov     [rsp+280h+var_260], 5
0x180097112  mov     rdi, [rsi+58h]
0x180097116  mov     rbx, [rdi+8]
0x18009711a  cmp     byte ptr [rbx+19h], 0
0x18009711e  jnz     short loc_180097149
0x180097120  lea     rcx, [rbx+20h]
0x180097124  lea     rdx, [rbp+180h+var_150]
0x180097128  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x18009712d  test    al, al
0x18009712f  jz      short loc_180097137
0x180097131  mov     rbx, [rbx+10h]
0x180097135  jmp     short loc_18009713D
0x180097137  mov     rdi, rbx
0x18009713a  mov     rbx, [rbx]
0x18009713d  cmp     byte ptr [rbx+19h], 0
0x180097141  jz      short loc_180097120
0x180097143  mov     rax, [rsi+58h]
0x180097147  jmp     short loc_18009714C
0x180097149  mov     rax, rdi
0x18009714c  cmp     byte ptr [rdi+19h], 0
0x180097150  jnz     short loc_180097169
0x180097152  lea     rdx, [rdi+20h]
0x180097156  lea     rcx, [rbp+180h+var_150]
0x18009715a  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x18009715f  test    al, al
0x180097161  jz      short loc_18009716C
0x180097163  mov     rdi, [rsi+58h]
0x180097167  jmp     short loc_18009716C
0x180097169  mov     rdi, rax
0x18009716c  cmp     rdi, [rsi+58h]
0x180097170  jz      short loc_1800971A1
0x180097172  lea     r8, [rdi+40h]
0x180097176  lea     rax, [rbp+180h+var_90]
0x18009717d  cmp     rax, r8
0x180097180  jz      short loc_1800971A1
0x180097182  cmp     qword ptr [r8+18h], 7
0x180097187  jbe     short loc_18009718E
0x180097189  mov     rdx, [r8]
0x18009718c  jmp     short loc_180097191
0x18009718e  mov     rdx, r8
0x180097191  mov     r8, [r8+10h]
0x180097195  lea     rcx, [rbp+180h+var_90]
0x18009719c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800971a1  lea     rdx, [rbp+180h+var_90]
0x1800971a8  mov     rcx, r15
0x1800971ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800971b0  mov     [rsp+280h+var_260], 1
0x1800971b8  mov     rdx, [rbp+180h+var_78]
0x1800971bf  cmp     rdx, 7
0x1800971c3  jbe     short loc_180097204
0x1800971c5  mov     rax, [rbp+180h+var_90]
0x1800971cc  lea     rdx, ds:2[rdx*2]
0x1800971d4  cmp     rdx, 1000h
0x1800971db  jb      short loc_1800971FB
0x1800971dd  mov     rcx, [rax-8]
0x1800971e1  sub     rax, rcx
0x1800971e4  sub     rax, 8
0x1800971e8  cmp     rax, 1Fh
0x1800971ec  ja      short loc_1800971F4
0x1800971ee  add     rdx, 27h ; '''
0x1800971f2  jmp     short loc_1800971FE
0x1800971f4  mov     ecx, 5
0x1800971f9  int     29h; Win8: RtlFailFast(ecx)
0x1800971fb  mov     rcx, rax; Block
0x1800971fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180097203  nop
0x180097204  mov     rdx, [rbp+180h+var_138]
0x180097208  cmp     rdx, 7
0x18009720c  jbe     short loc_180097246
0x18009720e  mov     rax, [rbp+180h+var_150]
0x180097212  lea     rdx, ds:2[rdx*2]
0x18009721a  cmp     rdx, 1000h
0x180097221  jb      short loc_18009723E
0x180097223  mov     rcx, [rax-8]
0x180097227  sub     rax, rcx
0x18009722a  sub     rax, 8
0x18009722e  cmp     rax, 1Fh
0x180097232  ja      loc_1800978EB
0x180097238  add     rdx, 27h ; '''
0x18009723c  jmp     short loc_180097241
0x18009723e  mov     rcx, rax; Block
0x180097241  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180097246  xorps   xmm0, xmm0
0x180097249  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x18009724d  mov     [rbp+180h+var_140], r12
0x180097251  mov     [rbp+180h+var_138], r12
0x180097255  lea     rcx, ?ms_header_copy_source@protocol@storage@azure@@3QBGB; "x-ms-copy-source"
0x18009725c  call    wcslen_0
0x180097261  mov     r8, rax
0x180097264  lea     rdx, ?ms_header_copy_source@protocol@storage@azure@@3QBGB; "x-ms-copy-source"
0x18009726b  lea     rcx, [rbp+180h+var_150]
0x18009726f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180097274  nop
0x180097275  xorps   xmm0, xmm0
0x180097278  movups  xmmword ptr [rbp+180h+var_70], xmm0
0x18009727f  mov     [rbp+180h+var_60], r12
0x180097286  mov     [rbp+180h+var_58], 7
0x180097291  mov     word ptr [rbp+180h+var_70], r12w
0x180097299  mov     [rsp+280h+var_260], 9
0x1800972a1  mov     rdi, [rsi+58h]
0x1800972a5  mov     rbx, [rdi+8]
0x1800972a9  cmp     byte ptr [rbx+19h], 0
0x1800972ad  jnz     short loc_1800972D9
0x1800972af  nop
0x1800972b0  lea     rcx, [rbx+20h]
0x1800972b4  lea     rdx, [rbp+180h+var_150]
0x1800972b8  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x1800972bd  test    al, al
0x1800972bf  jz      short loc_1800972C7
0x1800972c1  mov     rbx, [rbx+10h]
0x1800972c5  jmp     short loc_1800972CD
0x1800972c7  mov     rdi, rbx
0x1800972ca  mov     rbx, [rbx]
0x1800972cd  cmp     byte ptr [rbx+19h], 0
0x1800972d1  jz      short loc_1800972B0
0x1800972d3  mov     rax, [rsi+58h]
0x1800972d7  jmp     short loc_1800972DC
0x1800972d9  mov     rax, rdi
0x1800972dc  cmp     byte ptr [rdi+19h], 0
0x1800972e0  jnz     short loc_1800972F9
0x1800972e2  lea     rdx, [rdi+20h]
0x1800972e6  lea     rcx, [rbp+180h+var_150]
0x1800972ea  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x1800972ef  test    al, al
0x1800972f1  jz      short loc_1800972FC
0x1800972f3  mov     rdi, [rsi+58h]
0x1800972f7  jmp     short loc_1800972FC
0x1800972f9  mov     rdi, rax
0x1800972fc  cmp     rdi, [rsi+58h]
0x180097300  jz      short loc_180097331
0x180097302  lea     r8, [rdi+40h]
0x180097306  lea     rax, [rbp+180h+var_70]
0x18009730d  cmp     rax, r8
0x180097310  jz      short loc_180097331
0x180097312  cmp     qword ptr [r8+18h], 7
0x180097317  jbe     short loc_18009731E
0x180097319  mov     rdx, [r8]
0x18009731c  jmp     short loc_180097321
0x18009731e  mov     rdx, r8
0x180097321  mov     r8, [r8+10h]
0x180097325  lea     rcx, [rbp+180h+var_70]
0x18009732c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180097331  lea     rcx, [r15+60h]
0x180097335  lea     rdx, [rbp+180h+var_70]
0x18009733c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180097341  mov     [rsp+280h+var_260], 1
0x180097349  mov     rdx, [rbp+180h+var_58]
0x180097350  cmp     rdx, 7
0x180097354  jbe     short loc_180097395
  ... truncated ...
```
