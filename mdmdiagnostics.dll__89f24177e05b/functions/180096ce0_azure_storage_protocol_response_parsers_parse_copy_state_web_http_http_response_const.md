# azure::storage::protocol::response_parsers::parse_copy_state(web::http::http_response const &)

- ea: `0x180096ce0`
- end: `0x180097a15`
- name: `?parse_copy_state@response_parsers@protocol@storage@azure@@SA?AVcopy_state@34@AEBVhttp_response@http@web@@@Z`
- size: `3381`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800735a0`

## callees

- `0x180019000`
- `0x180019508`
- `0x180020e70`
- `0x180021ec0`
- `0x180072ad0`
- `0x180094fb0`
- `0x180096b40`
- `0x180096ce0`
- `0x1800a9e80`
- `0x1800e5248`
- `0x1800e533c`
- `0x1800e7a1c`
- `0x1800ee860`
- `0x1800f6c44`
- `0x1800f97d0`
- `0x18010776c`

## import_xrefs

- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18009792f`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18009792f`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18009788e`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18009788e`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097939`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180097939`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x1800978de`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x1800978f8`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x1800978de`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEA_J@Z` at `0x1800978f8`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18009786f`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18009786f`

## string_xrefs

- `0x180096f36`: `x-ms-copy-id`
- `0x180096f45`: `x-ms-copy-id`
- `0x180097256`: `x-ms-copy-completion-time`
- `0x180097265`: `x-ms-copy-completion-time`
- `0x180096d4d`: `x-ms-copy-status`
- `0x180096d5c`: `x-ms-copy-status`
- `0x180097779`: `x-ms-copy-progress`
- `0x180097788`: `x-ms-copy-progress`
- `0x180097411`: `x-ms-copy-status-description`
- `0x180097420`: `x-ms-copy-status-description`
- `0x1800970c5`: `x-ms-copy-source`
- `0x1800970d4`: `x-ms-copy-source`
- `0x1800975a6`: `x-ms-copy-destination-snapshot`
- `0x1800975b5`: `x-ms-copy-destination-snapshot`

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
0x180096ce0  mov     [rsp-8+arg_10], rbx
0x180096ce5  mov     [rsp-8+arg_18], rsi
0x180096cea  push    rbp
0x180096ceb  push    rdi
0x180096cec  push    r12
0x180096cee  push    r14
0x180096cf0  push    r15
0x180096cf2  lea     rbp, [rsp-160h]
0x180096cfa  sub     rsp, 260h
0x180096d01  mov     rax, cs:__security_cookie
0x180096d08  xor     rax, rsp
0x180096d0b  mov     [rbp+180h+var_30], rax
0x180096d12  mov     rbx, rdx
0x180096d15  mov     r15, rcx
0x180096d18  mov     [rsp+280h+var_248], rcx
0x180096d1d  xor     r12d, r12d
0x180096d20  mov     [rsp+280h+var_260], r12d
0x180096d25  call    ??0copy_state@storage@azure@@QEAA@XZ; azure::storage::copy_state::copy_state(void)
0x180096d2a  mov     [rsp+280h+var_260], 1
0x180096d32  mov     rsi, [rbx]
0x180096d35  xorps   xmm0, xmm0
0x180096d38  movups  xmmword ptr [rbp+180h+Block], xmm0
0x180096d3f  mov     [rbp+180h+var_C0], r12
0x180096d46  mov     [rbp+180h+var_B8], r12
0x180096d4d  lea     rcx, ?ms_header_copy_status@protocol@storage@azure@@3QBGB; "x-ms-copy-status"
0x180096d54  call    wcslen_0
0x180096d59  mov     r8, rax
0x180096d5c  lea     rdx, ?ms_header_copy_status@protocol@storage@azure@@3QBGB; "x-ms-copy-status"
0x180096d63  lea     rcx, [rbp+180h+Block]
0x180096d6a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180096d6f  nop
0x180096d70  lea     r8, [rbp+180h+Block]
0x180096d77  lea     rdx, [rsi+58h]
0x180096d7b  lea     rcx, [rbp+180h+S1]
0x180096d7f  call    ?get_header_value@protocol@storage@azure@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVhttp_headers@http@web@@AEBV45@@Z; azure::storage::protocol::get_header_value(web::http::http_headers const &,std::wstring const &)
0x180096d84  nop
0x180096d85  mov     rdx, [rbp+180h+var_B8]
0x180096d8c  cmp     rdx, 7
0x180096d90  jbe     short loc_180096DCD
0x180096d92  mov     rax, [rbp+180h+Block]
0x180096d99  lea     rdx, ds:2[rdx*2]
0x180096da1  cmp     rdx, 1000h
0x180096da8  jb      short loc_180096DC5
0x180096daa  mov     rcx, [rax-8]
0x180096dae  sub     rax, rcx
0x180096db1  sub     rax, 8
0x180096db5  cmp     rax, 1Fh
0x180096db9  ja      loc_18009775B
0x180096dbf  add     rdx, 27h ; '''
0x180096dc3  jmp     short loc_180096DC8
0x180096dc5  mov     rcx, rax; Block
0x180096dc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180096dcd  mov     [rbp+180h+var_C0], r12
0x180096dd4  mov     [rbp+180h+var_B8], 7
0x180096ddf  mov     word ptr [rbp+180h+Block], r12w
0x180096de7  mov     rbx, [rbp+180h+N]
0x180096deb  test    rbx, rbx
0x180096dee  jz      loc_1800979A4
0x180096df4  lea     rcx, ?header_value_copy_pending@protocol@storage@azure@@3QBGB; "pending"
0x180096dfb  call    wcslen_0
0x180096e00  mov     rdi, [rbp+180h+var_118]
0x180096e04  lea     rcx, [rbp+180h+S1]
0x180096e08  mov     r14, [rbp+180h+S1]
0x180096e0c  cmp     rdi, 7
0x180096e10  cmova   rcx, r14; S1
0x180096e14  cmp     rbx, rax
0x180096e17  jnz     short loc_180096E45
0x180096e19  test    rbx, rbx
0x180096e1c  jz      loc_180096F0B
0x180096e22  mov     r8, rbx; N
0x180096e25  lea     rdx, ?header_value_copy_pending@protocol@storage@azure@@3QBGB; "pending"
0x180096e2c  call    wmemcmp
0x180096e31  test    eax, eax
0x180096e33  jz      loc_180096F0B
0x180096e39  mov     rdi, [rbp+180h+var_118]
0x180096e3d  mov     rbx, [rbp+180h+N]
0x180096e41  mov     r14, [rbp+180h+S1]
0x180096e45  lea     rcx, ?header_value_copy_success@protocol@storage@azure@@3QBGB; "success"
0x180096e4c  call    wcslen_0
0x180096e51  lea     rcx, [rbp+180h+S1]
0x180096e55  cmp     rdi, 7
0x180096e59  cmova   rcx, r14; S1
0x180096e5d  cmp     rbx, rax
0x180096e60  jnz     short loc_180096E8E
0x180096e62  test    rbx, rbx
0x180096e65  jz      loc_180096F12
0x180096e6b  mov     r8, rbx; N
0x180096e6e  lea     rdx, ?header_value_copy_success@protocol@storage@azure@@3QBGB; "success"
0x180096e75  call    wmemcmp
0x180096e7a  test    eax, eax
0x180096e7c  jz      loc_180096F12
0x180096e82  mov     rdi, [rbp+180h+var_118]
0x180096e86  mov     rbx, [rbp+180h+N]
0x180096e8a  mov     r14, [rbp+180h+S1]
0x180096e8e  lea     rcx, ?header_value_copy_aborted@protocol@storage@azure@@3QBGB; "aborted"
0x180096e95  call    wcslen_0
0x180096e9a  lea     rcx, [rbp+180h+S1]
0x180096e9e  cmp     rdi, 7
0x180096ea2  cmova   rcx, r14; S1
0x180096ea6  cmp     rbx, rax
0x180096ea9  jnz     short loc_180096ECF
0x180096eab  test    rbx, rbx
0x180096eae  jz      short loc_180096F19
0x180096eb0  mov     r8, rbx; N
0x180096eb3  lea     rdx, ?header_value_copy_aborted@protocol@storage@azure@@3QBGB; "aborted"
0x180096eba  call    wmemcmp
0x180096ebf  test    eax, eax
0x180096ec1  jz      short loc_180096F19
0x180096ec3  mov     rdi, [rbp+180h+var_118]
0x180096ec7  mov     rbx, [rbp+180h+N]
0x180096ecb  mov     r14, [rbp+180h+S1]
0x180096ecf  lea     rcx, ?header_value_copy_failed@protocol@storage@azure@@3QBGB; "failed"
0x180096ed6  call    wcslen_0
0x180096edb  lea     rcx, [rbp+180h+S1]
0x180096edf  cmp     rdi, 7
0x180096ee3  cmova   rcx, r14; S1
0x180096ee7  cmp     rbx, rax
0x180096eea  jnz     short loc_180096F20
0x180096eec  test    rbx, rbx
0x180096eef  jz      short loc_180096F04
0x180096ef1  mov     r8, rbx; N
0x180096ef4  lea     rdx, ?header_value_copy_failed@protocol@storage@azure@@3QBGB; "failed"
0x180096efb  call    wmemcmp
0x180096f00  test    eax, eax
0x180096f02  jnz     short loc_180096F20
0x180096f04  mov     eax, 4
0x180096f09  jmp     short loc_180096F23
0x180096f0b  mov     eax, 1
0x180096f10  jmp     short loc_180096F23
0x180096f12  mov     eax, 2
0x180096f17  jmp     short loc_180096F23
0x180096f19  mov     eax, 3
0x180096f1e  jmp     short loc_180096F23
0x180096f20  mov     eax, r12d
0x180096f23  mov     [r15+58h], eax
0x180096f27  xorps   xmm0, xmm0
0x180096f2a  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x180096f2e  mov     [rbp+180h+var_140], r12
0x180096f32  mov     [rbp+180h+var_138], r12
0x180096f36  lea     rcx, ?ms_header_copy_id@protocol@storage@azure@@3QBGB; "x-ms-copy-id"
0x180096f3d  call    wcslen_0
0x180096f42  mov     r8, rax
0x180096f45  lea     rdx, ?ms_header_copy_id@protocol@storage@azure@@3QBGB; "x-ms-copy-id"
0x180096f4c  lea     rcx, [rbp+180h+var_150]
0x180096f50  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180096f55  nop
0x180096f56  xorps   xmm0, xmm0
0x180096f59  movups  xmmword ptr [rbp+180h+var_90], xmm0
0x180096f60  mov     [rbp+180h+var_80], r12
0x180096f67  mov     [rbp+180h+var_78], 7
0x180096f72  mov     word ptr [rbp+180h+var_90], r12w
0x180096f7a  mov     [rsp+280h+var_260], 5
0x180096f82  mov     rdi, [rsi+58h]
0x180096f86  mov     rbx, [rdi+8]
0x180096f8a  cmp     byte ptr [rbx+19h], 0
0x180096f8e  jnz     short loc_180096FB9
0x180096f90  lea     rcx, [rbx+20h]
0x180096f94  lea     rdx, [rbp+180h+var_150]
0x180096f98  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x180096f9d  test    al, al
0x180096f9f  jz      short loc_180096FA7
0x180096fa1  mov     rbx, [rbx+10h]
0x180096fa5  jmp     short loc_180096FAD
0x180096fa7  mov     rdi, rbx
0x180096faa  mov     rbx, [rbx]
0x180096fad  cmp     byte ptr [rbx+19h], 0
0x180096fb1  jz      short loc_180096F90
0x180096fb3  mov     rax, [rsi+58h]
0x180096fb7  jmp     short loc_180096FBC
0x180096fb9  mov     rax, rdi
0x180096fbc  cmp     byte ptr [rdi+19h], 0
0x180096fc0  jnz     short loc_180096FD9
0x180096fc2  lea     rdx, [rdi+20h]
0x180096fc6  lea     rcx, [rbp+180h+var_150]
0x180096fca  call    ?str_iless@details@utility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; utility::details::str_iless(std::wstring const &,std::wstring const &)
0x180096fcf  test    al, al
0x180096fd1  jz      short loc_180096FDC
0x180096fd3  mov     rdi, [rsi+58h]
0x180096fd7  jmp     short loc_180096FDC
0x180096fd9  mov     rdi, rax
0x180096fdc  cmp     rdi, [rsi+58h]
0x180096fe0  jz      short loc_180097011
0x180096fe2  lea     r8, [rdi+40h]
0x180096fe6  lea     rax, [rbp+180h+var_90]
0x180096fed  cmp     rax, r8
0x180096ff0  jz      short loc_180097011
0x180096ff2  cmp     qword ptr [r8+18h], 7
0x180096ff7  jbe     short loc_180096FFE
0x180096ff9  mov     rdx, [r8]
0x180096ffc  jmp     short loc_180097001
0x180096ffe  mov     rdx, r8
0x180097001  mov     r8, [r8+10h]
0x180097005  lea     rcx, [rbp+180h+var_90]
0x18009700c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180097011  lea     rdx, [rbp+180h+var_90]
0x180097018  mov     rcx, r15
0x18009701b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180097020  mov     [rsp+280h+var_260], 1
0x180097028  mov     rdx, [rbp+180h+var_78]
0x18009702f  cmp     rdx, 7
0x180097033  jbe     short loc_180097074
0x180097035  mov     rax, [rbp+180h+var_90]
0x18009703c  lea     rdx, ds:2[rdx*2]
0x180097044  cmp     rdx, 1000h
0x18009704b  jb      short loc_18009706B
0x18009704d  mov     rcx, [rax-8]
0x180097051  sub     rax, rcx
0x180097054  sub     rax, 8
0x180097058  cmp     rax, 1Fh
0x18009705c  ja      short loc_180097064
0x18009705e  add     rdx, 27h ; '''
0x180097062  jmp     short loc_18009706E
0x180097064  mov     ecx, 5
0x180097069  int     29h; Win8: RtlFailFast(ecx)
0x18009706b  mov     rcx, rax; Block
0x18009706e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180097073  nop
0x180097074  mov     rdx, [rbp+180h+var_138]
0x180097078  cmp     rdx, 7
0x18009707c  jbe     short loc_1800970B6
0x18009707e  mov     rax, [rbp+180h+var_150]
0x180097082  lea     rdx, ds:2[rdx*2]
0x18009708a  cmp     rdx, 1000h
0x180097091  jb      short loc_1800970AE
0x180097093  mov     rcx, [rax-8]
0x180097097  sub     rax, rcx
0x18009709a  sub     rax, 8
0x18009709e  cmp     rax, 1Fh
0x1800970a2  ja      loc_18009775B
0x1800970a8  add     rdx, 27h ; '''
0x1800970ac  jmp     short loc_1800970B1
0x1800970ae  mov     rcx, rax; Block
0x1800970b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800970b6  xorps   xmm0, xmm0
0x1800970b9  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x1800970bd  mov     [rbp+180h+var_140], r12
0x1800970c1  mov     [rbp+180h+var_138], r12
0x1800970c5  lea     rcx, ?ms_header_copy_source@protocol@storage@azure@@3QBGB; "x-ms-copy-source"
0x1800970cc  call    wcslen_0
0x1800970d1  mov     r8, rax
0x1800970d4  lea     rdx, ?ms_header_copy_source@protocol@storage@azure@@3QBGB; "x-ms-copy-source"
0x1800970db  lea     rcx, [rbp+180h+var_150]
0x1800970df  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800970e4  nop
0x1800970e5  xorps   xmm0, xmm0
0x1800970e8  movups  xmmword ptr [rbp+180h+var_70], xmm0
0x1800970ef  mov     [rbp+180h+var_60], r12
0x1800970f6  mov     [rbp+180h+var_58], 7
0x180097101  mov     word ptr [rbp+180h+var_70], r12w
0x180097109  mov     [rsp+280h+var_260], 9
0x180097111  mov     rdi, [rsi+58h]
0x180097115  mov     rbx, [rdi+8]
0x180097119  cmp     byte ptr [rbx+19h], 0
0x18009711d  jnz     short loc_180097149
0x18009711f  nop
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
0x180097176  lea     rax, [rbp+180h+var_70]
0x18009717d  cmp     rax, r8
0x180097180  jz      short loc_1800971A1
0x180097182  cmp     qword ptr [r8+18h], 7
0x180097187  jbe     short loc_18009718E
0x180097189  mov     rdx, [r8]
0x18009718c  jmp     short loc_180097191
0x18009718e  mov     rdx, r8
0x180097191  mov     r8, [r8+10h]
0x180097195  lea     rcx, [rbp+180h+var_70]
0x18009719c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800971a1  lea     rcx, [r15+60h]
0x1800971a5  lea     rdx, [rbp+180h+var_70]
0x1800971ac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800971b1  mov     [rsp+280h+var_260], 1
0x1800971b9  mov     rdx, [rbp+180h+var_58]
0x1800971c0  cmp     rdx, 7
0x1800971c4  jbe     short loc_180097205
  ... truncated ...
```
