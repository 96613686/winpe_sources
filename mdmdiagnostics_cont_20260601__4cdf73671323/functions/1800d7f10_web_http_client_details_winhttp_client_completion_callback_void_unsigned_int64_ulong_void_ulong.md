# web::http::client::details::winhttp_client::completion_callback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x1800d7f10`
- end: `0x1800d9665`
- name: `?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z`
- size: `5973`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019e4e`
- `0x180019ff4`
- `0x180020470`
- `0x18004c230`
- `0x1800bad10`
- `0x1800bcc50`
- `0x1800bd230`
- `0x1800bd240`
- `0x1800bd380`
- `0x1800bdc50`
- `0x1800be450`
- `0x1800cdb60`
- `0x1800d2070`
- `0x1800d3130`
- `0x1800d3240`
- `0x1800d5970`
- `0x1800d6a60`
- `0x1800d6b50`
- `0x1800d7220`
- `0x1800d7970`
- `0x1800d79d0`
- `0x1800d7bd0`
- `0x1800d7e70`
- `0x1800d7f10`
- `0x1800d9a40`
- `0x1800d9e60`
- `0x1800db4f0`
- `0x1800dc8f0`
- `0x1800dcee0`
- `0x1800dd230`
- `0x1800e460c`
- `0x1800e5110`
- `0x1800e52a8`
- `0x1800e79d4`
- `0x1800ee898`
- `0x18013e8bc`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpQueryHeaders` at `0x1800d806e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d80b2`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d8484`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d84c8`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d806e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d80b2`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d8484`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800d84c8`
- `WINHTTP!WinHttpReadData` at `0x1800d8708`
- `WINHTTP!WinHttpReadData` at `0x1800d8708`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d8c2f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d8e86`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d8c2f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d8e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d80c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d84d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d80c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d84d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8e94`

## string_xrefs

- `0x1800d873e`: `WinHttpReadData`
- `0x1800d89ae`: `Received incomplete compressed stream`
- `0x1800d9115`: `Received incomplete compressed stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall web::http::client::details::winhttp_client::completion_callback(
        HINTERNET hInternet,
        std::_Ref_count_base **dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  volatile signed __int32 *v7; // rdx
  __m128i si128; // xmm6
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  __m128i v11; // xmm0
  std::_Ref_count_base *v12; // r14
  volatile signed __int32 *v13; // rdi
  web::http::details *v14; // rsi
  DWORD v15; // ebx
  __int64 v16; // rax
  void *v17; // rcx
  __int16 v18; // cx
  void *v19; // rcx
  _QWORD *v20; // rax
  __int64 security_failure_message; // rax
  void *v22; // rcx
  void *v23; // rax
  __int64 v24; // rax
  web::http::details *v25; // rbx
  DWORD LastError; // ebx
  __int64 v27; // rax
  void *v28; // rcx
  unsigned __int64 v29; // rsi
  void *v30; // rbx
  __int64 v31; // rax
  DWORD v32; // ebx
  __int64 v33; // r8
  void *v34; // rcx
  void *v35; // rcx
  char *v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  volatile signed __int32 *v40; // rbx
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  volatile signed __int32 *v44; // rbx
  bool v45; // r12
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rcx
  std::_Ref_count_base *v49; // rbx
  int v50; // eax
  DWORD v51; // ebx
  __int64 v52; // rax
  unsigned int v53; // esi
  __int64 v54; // rax
  void *v55; // rcx
  __int64 v56; // r12
  __int64 v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rcx
  volatile signed __int32 *v60; // rbx
  __int64 readbuffer; // rax
  __int64 v62; // rdx
  int v63; // eax
  DWORD v64; // ebx
  __int64 v65; // rax
  void *v66; // rcx
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rcx
  void *v70; // rcx
  unsigned __int64 v71; // rcx
  unsigned __int64 v72; // rax
  __int64 v73; // rax
  volatile signed __int32 *v74; // r14
  volatile signed __int32 *v75; // r14
  volatile signed __int32 *v76; // r14
  __int64 v77; // r8
  volatile signed __int32 *v78; // r14
  volatile signed __int32 *v79; // r14
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-1A8h] BYREF
  void *v85[2]; // [rsp+40h] [rbp-198h] BYREF
  LPVOID lpBuffer[2]; // [rsp+50h] [rbp-188h] BYREF
  __int128 v87; // [rsp+60h] [rbp-178h]
  std::_Ref_count_base *v88[2]; // [rsp+70h] [rbp-168h] BYREF
  __int64 v89; // [rsp+80h] [rbp-158h]
  std::_Ref_count_base *v90; // [rsp+88h] [rbp-150h]
  _BYTE v91[8]; // [rsp+90h] [rbp-148h] BYREF
  volatile signed __int32 *v92; // [rsp+98h] [rbp-140h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v94[24]; // [rsp+B8h] [rbp-120h] BYREF
  _BYTE v95[24]; // [rsp+D0h] [rbp-108h] BYREF
  void *Block[2]; // [rsp+E8h] [rbp-F0h] BYREF
  __int128 v97; // [rsp+F8h] [rbp-E0h]
  void *Src[2]; // [rsp+108h] [rbp-D0h] BYREF
  volatile signed __int32 *v99; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v100; // [rsp+120h] [rbp-B8h]
  void **v101; // [rsp+130h] [rbp-A8h] BYREF
  __int128 v102; // [rsp+138h] [rbp-A0h] BYREF
  int v103; // [rsp+148h] [rbp-90h]
  void ***v104; // [rsp+150h] [rbp-88h]
  void *v105[2]; // [rsp+158h] [rbp-80h] BYREF
  __int128 v106; // [rsp+168h] [rbp-70h]

  if ( !dwContext )
    return;
  v7 = (volatile signed __int32 *)dwContext[1];
  if ( dwInternetStatus == 2048 )
  {
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    operator delete(dwContext);
    return;
  }
  si128 = 0;
  *(_OWORD *)v88 = 0;
  if ( v7 && (v9 = *((_DWORD *)v7 + 2)) != 0 )
  {
    while ( 1 )
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange(v7 + 2, v9 + 1, v9);
      if ( v10 == v9 )
        break;
      if ( !v9 )
      {
        v11 = 0;
        goto LABEL_14;
      }
    }
    v12 = *dwContext;
    v88[0] = *dwContext;
    v13 = (volatile signed __int32 *)dwContext[1];
    v88[1] = (std::_Ref_count_base *)v13;
    si128 = _mm_load_si128((const __m128i *)v88);
  }
  else
  {
    v11 = 0;
LABEL_14:
    v12 = 0;
    v13 = (volatile signed __int32 *)_mm_srli_si128(v11, 8).m128i_u64[0];
  }
  if ( !v12 )
  {
    if ( !v13 )
      return;
LABEL_247:
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    return;
  }
  if ( dwInternetStatus <= 0x40000 )
  {
    if ( dwInternetStatus != 0x40000 )
    {
      if ( dwInternetStatus == 16 )
      {
        web::http::client::details::winhttp_request_context::on_send_request_validate_cn(v12);
        if ( !v13 )
          return;
        goto LABEL_247;
      }
      if ( dwInternetStatus == 0x4000 )
      {
        v24 = *((_QWORD *)v12 + 16);
        if ( v24 )
        {
          *((_QWORD *)v12 + 16) = v24 - 1;
          if ( !v13 )
            return;
          goto LABEL_247;
        }
        dwBufferLength[0] = 0;
        WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
        *(_OWORD *)lpBuffer = 0;
        *(_QWORD *)&v87 = 0;
        std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
        v25 = (web::http::details *)lpBuffer[0];
        if ( WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
        {
          web::http::client::details::parse_winhttp_headers(hInternet, v25);
          web::http::client::details::request_context::complete_headers(v12);
          web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
          web::http::client::details::request_context::complete_request(v12, 0);
          web::http::client::details::winhttp_request_context::cleanup(v12);
        }
        else
        {
          LastError = GetLastError();
          *(_OWORD *)Block = 0;
          v85[0] = (void *)31;
          Block[0] = (void *)std::string::_Allocate_for_capacity<0>(Block, v85);
          *(_QWORD *)&v97 = 19;
          *((void **)&v97 + 1) = v85[0];
          strcpy((char *)Block[0], "WinHttpQueryHeaders");
          v27 = web::http::client::details::build_error_msg(Src);
          web::http::client::details::request_context::report_error(v12, LastError, v27);
          std::string::~string(Src);
          std::string::~string(Block);
        }
        goto LABEL_65;
      }
      if ( dwInternetStatus != 0x10000 )
      {
        if ( dwInternetStatus == 0x20000 )
        {
          dwBufferLength[0] = 0;
          WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
          *(_OWORD *)lpBuffer = 0;
          *(_QWORD *)&v87 = 0;
          std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
          v14 = (web::http::details *)lpBuffer[0];
          if ( !WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
          {
            v15 = GetLastError();
            *(_OWORD *)Block = 0;
            v97 = 0u;
            std::string::_Construct<1,char const *>(Block, "WinHttpQueryHeaders", 19);
            v16 = web::http::client::details::build_error_msg(Src);
            web::http::client::details::request_context::report_error(v12, v15, v16);
            std::string::~string(Src);
            if ( *((_QWORD *)&v97 + 1) > 0xFu )
            {
              if ( (unsigned __int64)(*((_QWORD *)&v97 + 1) + 1LL) < 0x1000 )
              {
                v17 = Block[0];
              }
              else
              {
                v17 = (void *)*((_QWORD *)Block[0] - 1);
                if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
                  __fastfail(5u);
              }
              operator delete(v17);
            }
LABEL_65:
            if ( !lpBuffer[0] )
              goto LABEL_71;
            if ( (unsigned __int64)v87 - (unsigned __int64)lpBuffer[0] < 0x1000 )
            {
              v28 = lpBuffer[0];
LABEL_70:
              operator delete(v28);
              *(_OWORD *)lpBuffer = 0;
              *(_QWORD *)&v87 = 0;
LABEL_71:
              if ( v13 )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
              return;
            }
            v28 = (void *)*((_QWORD *)lpBuffer[0] - 1);
            if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v28 - 8) <= 0x1F )
              goto LABEL_70;
LABEL_180:
            __fastfail(5u);
          }
          web::http::client::details::parse_winhttp_headers(hInternet, v14);
          v18 = *(_WORD *)(*((_QWORD *)v12 + 5) + 136LL);
          if ( v18 == 401 || v18 == 407 )
          {
            if ( (unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                                    hInternet,
                                    v88,
                                    0) )
            {
              if ( lpBuffer[0] )
              {
                if ( (unsigned __int64)v87 - (unsigned __int64)lpBuffer[0] < 0x1000 )
                {
                  v19 = lpBuffer[0];
                }
                else
                {
                  v19 = (void *)*((_QWORD *)lpBuffer[0] - 1);
                  if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v19 - 8) > 0x1F )
                    goto LABEL_180;
                }
                operator delete(v19);
                *(_OWORD *)lpBuffer = 0;
                *(_QWORD *)&v87 = 0;
              }
              goto LABEL_140;
            }
            v13 = (volatile signed __int32 *)v88[1];
            v12 = v88[0];
          }
          if ( web::http::client::details::request_context::handle_compression(v12) )
          {
            if ( *((_QWORD *)v12 + 12)
              && !*((_BYTE *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                                  + 1))
                  + 424) )
            {
              v20 = operator new(0x10u);
              v85[0] = v20;
              if ( v20 )
              {
                *v20 = 0;
                *((_DWORD *)v20 + 2) = 1;
                *((_BYTE *)v20 + 12) = 0;
              }
              else
              {
                v20 = 0;
              }
              v85[0] = v20;
              std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(
                (char *)v12 + 320,
                v85);
              if ( v85[0] )
                operator delete(v85[0]);
              *((_BYTE *)v12 + 307) = 1;
            }
            web::http::client::details::request_context::complete_headers(v12);
            if ( (unsigned __int8)std::operator==<unsigned short>(
                                    *((_QWORD *)v12 + 3) + 144LL,
                                    &web::http::methods::HEAD) )
            {
              web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
              web::http::client::details::request_context::complete_request(v12, 0);
            }
            else
            {
              web::http::client::details::winhttp_client::read_next_response_chunk(v12, 0, 1);
            }
          }
          goto LABEL_65;
        }
LABEL_121:
        if ( !v13 )
          return;
        goto LABEL_247;
      }
      security_failure_message = anonymous_namespace_::generate_security_failure_message(Src);
      v102 = 0;
      v101 = &web::http::http_exception::`vftable';
      v103 = 0;
      v104 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      *(_OWORD *)v105 = 0;
      v106 = 0u;
      v105[0] = *(void **)security_failure_message;
      v105[1] = *(void **)(security_failure_message + 8);
      v106 = *(_OWORD *)(security_failure_message + 16);
      *(_QWORD *)(security_failure_message + 24) = 15;
      *(_BYTE *)security_failure_message = 0;
      *(_QWORD *)(security_failure_message + 16) = 0;
      *(_QWORD *)(security_failure_message + 24) = 15;
      *(_BYTE *)security_failure_message = 0;
      web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v101);
      if ( *((_QWORD *)&v106 + 1) > 0xFu )
      {
        v22 = v105[0];
        if ( (unsigned __int64)(*((_QWORD *)&v106 + 1) + 1LL) < 0x1000 )
        {
LABEL_57:
          operator delete(v22);
          goto LABEL_58;
        }
        v23 = (void *)*((_QWORD *)v105[0] - 1);
        if ( (unsigned __int64)((char *)v105[0] - (char *)v23 - 8) > 0x1F )
          goto LABEL_180;
LABEL_56:
        v22 = v23;
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    v29 = (unsigned int)*lpvStatusInformation;
    if ( (_DWORD)v29 )
    {
      if ( *((_QWORD *)v12 + 12) )
      {
        if ( *((_QWORD *)v12 + 34) - *((_QWORD *)v12 + 32) < v29 )
          std::vector<unsigned char>::reserve((char *)v12 + 256, (unsigned int)v29);
        v30 = (void *)*((_QWORD *)v12 + 32);
      }
      else
      {
        web::http::client::details::request_context::_get_writebuffer(v12, Block);
        if ( !Block[1] )
        {
          std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
          throw (std::invalid_argument *)pExceptionObject;
        }
        v31 = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)Block[1] + 224LL))(Block[1], v29);
        if ( v31 )
        {
          *((_QWORD *)v12 + 31) = v29;
        }
        else
        {
          if ( v29 > *((_QWORD *)v12 + 29) - *((_QWORD *)v12 + 28) )
            std::vector<unsigned char>::resize((char *)v12 + 224, v29);
          v31 = 0;
        }
        *((_QWORD *)v12 + 27) = v31;
        v30 = (void *)v31;
        if ( !v31 )
          v30 = (void *)*((_QWORD *)v12 + 28);
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(Block);
      }
      if ( !WinHttpReadData(hInternet, v30, v29, 0) )
      {
        v32 = GetLastError();
        *(_QWORD *)&v97 = 15;
        *((_QWORD *)&v97 + 1) = 15;
        qmemcpy(Block, "WinHttpReadDat", 14);
        HIWORD(Block[1]) = (unsigned __int8)aWinhttpreaddat[14];
        v33 = web::http::client::details::build_error_msg(Src);
        web::http::client::details::request_context::report_error(v12, v32, v33);
        if ( v100 > 0xF )
        {
          if ( v100 + 1 < 0x1000 )
          {
            v34 = Src[0];
          }
          else
          {
            v34 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v34 - 8) > 0x1F )
              __fastfail(5u);
          }
          operator delete(v34);
        }
        v99 = 0;
        v100 = 15;
        LOBYTE(Src[0]) = 0;
        if ( *((_QWORD *)&v97 + 1) > 0xFu )
        {
          if ( (unsigned __int64)(*((_QWORD *)&v97 + 1) + 1LL) < 0x1000 )
          {
            operator delete(Block[0]);
          }
          else
          {
            v35 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v35 - 8) > 0x1F )
              goto LABEL_180;
            operator delete(v35);
          }
        }
      }
      goto LABEL_246;
    }
    if ( *((_QWORD *)v12 + 12) )
    {
      if ( *((_BYTE *)v12 + 307) )
      {
        v36 = (char *)operator new(0x30u);
        strcpy(v36, "Chunked response stream ended unexpectedly");
        v102 = 0;
        v101 = &web::http::http_exception::`vftable';
        v103 = 0;
        v104 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        v105[0] = v36;
        v105[1] = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        *(_QWORD *)&v106 = 42;
        *((_QWORD *)&v106 + 1) = 47;
        web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v101);
        if ( *((_QWORD *)&v106 + 1) > 0xFu )
        {
          v23 = v105[0];
          if ( (unsigned __int64)(*((_QWORD *)&v106 + 1) + 1LL) >= 0x1000 )
          {
            v22 = (void *)*((_QWORD *)v105[0] - 1);
            if ( (unsigned __int64)((char *)v105[0] - (char *)v22 - 8) > 0x1F )
              goto LABEL_180;
            goto LABEL_57;
          }
          goto LABEL_56;
        }
LABEL_58:
        *(_QWORD *)&v106 = 0;
        *((_QWORD *)&v106 + 1) = 15;
        LOBYTE(v105[0]) = 0;
        v101 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v102);
        if ( !v13 )
          return;
        goto LABEL_247;
      }
      if ( *((_BYTE *)v12 + 305) && !*((_BYTE *)v12 + 306) )
      {
        *(_OWORD *)Block = 0;
        v97 = 0u;
        std::string::_Construct<1,char const *>(Block, "Received incomplete compressed stream", 37);
        v102 = 0;
        v101 = &web::http::http_exception::`vftable';
        v103 = 0;
        v104 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        *(_OWORD *)v105 = *(_OWORD *)Block;
        v106 = v97;
        web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v101);
        std::string::~string(v105);
        v101 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v102);
        if ( v13 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
        return;
      }
    }
    v37 = *((_QWORD *)v12 + 3);
    v38 = *(_QWORD *)(v37 + 720);
    if ( v38 )
      _InterlockedIncrement((volatile signed __int32 *)(v38 + 8));
    v39 = *(_QWORD *)(v37 + 712);
    v89 = v39;
    v40 = *(volatile signed __int32 **)(v37 + 720);
    v90 = (std::_Ref_count_base *)v40;
    if ( v39 )
    {
      try
      {
        std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v39, 1);
      }
      catch ( ... )
      {
        v82 = std::current_exception(v85);
        web::http::client::details::request_context::report_exception(v88[0], v82);
        goto LABEL_138;
      }
    }
    web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
    if ( !v40 )
      goto LABEL_246;
LABEL_243:
    if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
    goto LABEL_246;
  }
  if ( dwInternetStatus != 0x80000 )
  {
    if ( dwInternetStatus == 0x100000 )
    {
      v56 = (unsigned int)*lpvStatusInformation;
      if ( (_DWORD)v56 )
      {
        v57 = *((_QWORD *)v12 + 3);
        v58 = *(_QWORD *)(v57 + 720);
        if ( v58 )
          _InterlockedIncrement((volatile signed __int32 *)(v58 + 8));
        v59 = *(_QWORD *)(v57 + 712);
        v89 = v59;
        v60 = *(volatile signed __int32 **)(v57 + 720);
        v90 = (std::_Ref_count_base *)v60;
        if ( v59 )
        {
          try
          {
            *((_QWORD *)v12 + 7) += v56;
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v59, 0);
          }
          catch ( ... )
          {
            v81 = std::current_exception(v85);
            web::http::client::details::request_context::report_exception(v88[0], v81);
            goto LABEL_138;
          }
        }
        if ( v60 )
        {
          if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
            if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
          }
        }
      }
      if ( *((_QWORD *)v12 + 27) )
      {
        readbuffer = web::http::client::details::winhttp_request_context::_get_readbuffer(v12, Block);
        v62 = *((_QWORD *)v12 + 27);
        if ( !v62 )
          v62 = *((_QWORD *)v12 + 28);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)readbuffer + 248LL))(readbuffer, v62, v56);
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(Block);
      }
      v63 = *((_DWORD *)v12 + 34);
      if ( v63 == 2 )
      {
LABEL_145:
        web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(v12);
        goto LABEL_246;
      }
      if ( v63 != 1 )
      {
        if ( !WinHttpReceiveResponse(hInternet, 0) )
        {
          v64 = GetLastError();
          *(_OWORD *)Block = 0;
          v85[0] = (void *)31;
          Block[0] = (void *)std::string::_Allocate_for_capacity<0>(Block, v85);
          *(_QWORD *)&v97 = 22;
          *((void **)&v97 + 1) = v85[0];
          strcpy((char *)Block[0], "WinHttpReceiveResponse");
          v65 = web::http::client::details::build_error_msg(Src);
          web::http::client::details::request_context::report_error(v12, v64, v65);
          std::string::~string(Src);
          if ( *((_QWORD *)&v97 + 1) > 0xFu )
          {
            if ( (unsigned __int64)(*((_QWORD *)&v97 + 1) + 1LL) < 0x1000 )
            {
              operator delete(Block[0]);
            }
            else
            {
              v66 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v66 - 8) > 0x1F )
                goto LABEL_180;
              operator delete(v66);
            }
          }
        }
LABEL_246:
        if ( !v13 )
          return;
        goto LABEL_247;
      }
LABEL_147:
      web::http::client::details::winhttp_client::_multiple_segment_write_data(v12);
      goto LABEL_246;
    }
    if ( dwInternetStatus != 0x200000 )
    {
      if ( dwInternetStatus != 0x400000 )
        goto LABEL_121;
      v41 = *((_QWORD *)v12 + 3);
      v42 = *(_QWORD *)(v41 + 56);
      if ( v42 )
        _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
      v43 = *(_QWORD *)(v41 + 48);
      v44 = *(volatile signed __int32 **)(v41 + 56);
      v45 = !v43 || !*(_QWORD *)(v43 + 8);
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      if ( v45 )
      {
        v46 = *((_QWORD *)v12 + 3);
        v47 = *(_QWORD *)(v46 + 720);
        if ( v47 )
          _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
        v48 = *(_QWORD *)(v46 + 712);
        v89 = v48;
        v49 = *(std::_Ref_count_base **)(v46 + 720);
        v90 = v49;
        if ( v48 )
        {
          try
          {
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v48, 0);
          }
          catch ( ... )
          {
            v80 = std::current_exception(v85);
            web::http::client::details::request_context::report_exception(v88[0], v80);
            goto LABEL_138;
          }
        }
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
      }
      v50 = *((_DWORD *)v12 + 34);
      if ( v50 == 2 )
        goto LABEL_145;
      if ( v50 != 1 )
      {
        if ( !WinHttpReceiveResponse(hInternet, 0) )
        {
          v51 = GetLastError();
          *(_OWORD *)Src = 0;
          v99 = 0;
          v100 = 0;
          std::string::_Construct<1,char const *>(Src, "WinHttpReceiveResponse", 22);
          v52 = web::http::client::details::build_error_msg(Block);
          web::http::client::details::request_context::report_error(v12, v51, v52);
          std::string::~string(Block);
          std::string::~string(Src);
        }
        goto LABEL_246;
      }
      goto LABEL_147;
    }
    v53 = lpvStatusInformation[2];
    if ( v53 != 12032 )
    {
LABEL_153:
      v54 = web::http::client::details::build_error_msg_0(Src);
      web::http::client::details::request_context::report_error(v12, v53, v54);
      if ( v100 > 0xF )
      {
        if ( v100 + 1 < 0x1000 )
        {
          v55 = Src[0];
        }
        else
        {
          v55 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v55 - 8) > 0x1F )
            goto LABEL_180;
        }
        operator delete(v55);
      }
      if ( !v13 )
        return;
      goto LABEL_247;
    }
    if ( !(unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                             hInternet,
                             v88,
                             12032) )
    {
      v13 = (volatile signed __int32 *)v88[1];
      v12 = v88[0];
      goto LABEL_153;
    }
LABEL_140:
    if ( v88[1] )
      std::_Ref_count_base::_Decref(v88[1]);
    return;
  }
  v67 = *((_QWORD *)v12 + 3);
  v68 = *(_QWORD *)(v67 + 720);
  if ( v68 )
    _InterlockedIncrement((volatile signed __int32 *)(v68 + 8));
  v89 = *(_QWORD *)(v67 + 712);
  v69 = v89;
  v40 = *(volatile signed __int32 **)(v67 + 720);
  v90 = (std::_Ref_count_base *)v40;
  *((_QWORD *)v12 + 8) += dwStatusInformationLength;
  if ( v69 )
  {
    try
    {
      std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v69, 1);
    }
    catch ( ... )
    {
      v83 = std::current_exception(v85);
      web::http::client::details::request_context::report_exception(v88[0], v83);
LABEL_138:
      if ( v90 )
        std::_Ref_count_base::_Decref(v90);
      goto LABEL_140;
    }
  }
  if ( dwStatusInformationLength )
  {
    web::http::client::details::request_context::_get_writebuffer(v12, Block);
    if ( *((_QWORD *)v12 + 12) )
    {
      v71 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                             + 1))
            + 52);
      if ( !v71 )
        v71 = 0x10000;
      v72 = dwStatusInformationLength;
      if ( dwStatusInformationLength < v71 )
        v72 = v71;
      *((_QWORD *)v12 + 36) = dwStatusInformationLength;
      *((_QWORD *)v12 + 39) = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      *(__m128i *)v85 = si128;
      *(_OWORD *)Src = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[0] = v12;
      Src[1] = (void *)v13;
      v99 = (volatile signed __int32 *)v72;
      v100 = v72;
      v73 = ____do_while_V_lambda_2___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__N_details_pplx__YA_AV__task__N_1_V_lambda_2___JB___completion_callback_winhttp_client_0client_http_web__CAXPEAX_KK0K_Z__Z(
              lpBuffer,
              Src);
      ___then_V_lambda_3___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__N_pplx__QEBA_AV__task_X_1___QEAV_lambda_3___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v73,
        v91,
        v85);
      v74 = v92;
      if ( v92 )
      {
        if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
          if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
        }
      }
      v75 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
          if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
        }
      }
      v76 = (volatile signed __int32 *)v85[1];
    }
    else
    {
      if ( *((_QWORD *)v12 + 27) )
      {
        if ( !Block[1] )
        {
          std::invalid_argument::invalid_argument((std::invalid_argument *)v94, "Invalid streambuf object");
          throw (std::invalid_argument *)v94;
        }
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)Block[1] + 232LL))(Block[1], dwStatusInformationLength);
        web::http::client::details::winhttp_client::read_next_response_chunk(v12, dwStatusInformationLength, 0);
        goto LABEL_241;
      }
      Src[0] = hInternet;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[1] = v12;
      v99 = v13;
      LODWORD(v100) = dwStatusInformationLength;
      v77 = *((_QWORD *)v12 + 27);
      if ( !v77 )
        v77 = *((_QWORD *)v12 + 28);
      if ( !Block[1] )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)v95, "Invalid streambuf object");
        throw (std::invalid_argument *)v95;
      }
      (*(void (__fastcall **)(void *, void **, __int64, _QWORD))(*(_QWORD *)Block[1] + 112LL))(
        Block[1],
        v85,
        v77,
        dwStatusInformationLength);
      ___then_V_lambda_4___JI___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_4___JI___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v85,
        lpBuffer,
        Src);
      v78 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
          if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
        }
      }
      v79 = (volatile signed __int32 *)v85[1];
      if ( v85[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v85[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
          if ( _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
        }
      }
      v76 = v99;
    }
    if ( v76 )
    {
      if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
        if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
      }
    }
LABEL_241:
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(Block);
LABEL_242:
    if ( !v40 )
      goto LABEL_246;
    goto LABEL_243;
  }
  if ( !*((_QWORD *)v12 + 12) )
    goto LABEL_201;
  if ( *((_BYTE *)v12 + 307) )
  {
    lpBuffer[1] = 0;
    lpBuffer[0] = operator new(0x30u);
    *(_QWORD *)&v87 = 42;
    *((_QWORD *)&v87 + 1) = 47;
    strcpy((char *)lpBuffer[0], "Chunked response stream ended unexpectedly");
    v102 = 0;
    v101 = &web::http::http_exception::`vftable';
    v103 = 0;
    v104 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v105 = *(_OWORD *)lpBuffer;
    v106 = v87;
    web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v101);
    std::string::~string(v105);
    v101 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v102);
    goto LABEL_242;
  }
  if ( !*((_BYTE *)v12 + 305) || *((_BYTE *)v12 + 306) )
  {
LABEL_201:
    web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
    goto LABEL_242;
  }
  *(_OWORD *)lpBuffer = 0;
  v87 = 0u;
  std::string::_Construct<1,char const *>(lpBuffer, "Received incomplete compressed stream", 37);
  v102 = 0;
  v101 = &web::http::http_exception::`vftable';
  v103 = 0;
  v104 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v105[0] = lpBuffer[0];
  v105[1] = lpBuffer[1];
  v106 = v87;
  web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v101);
  if ( *((_QWORD *)&v106 + 1) > 0xFu )
  {
    if ( (unsigned __int64)(*((_QWORD *)&v106 + 1) + 1LL) < 0x1000 )
    {
      v70 = v105[0];
    }
    else
    {
      v70 = (void *)*((_QWORD *)v105[0] - 1);
      if ( (unsigned __int64)((char *)v105[0] - (char *)v70 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v70);
  }
  *(_QWORD *)&v106 = 0;
  *((_QWORD *)&v106 + 1) = 15;
  LOBYTE(v105[0]) = 0;
  v101 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v102);
  if ( v40 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v40);
  if ( v13 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
}

```

## disassembly

```asm
0x1800d7f10  test    rdx, rdx
0x1800d7f13  jz      locret_1800D95E9
0x1800d7f19  push    rbx
0x1800d7f1a  push    rsi
0x1800d7f1b  push    rdi
0x1800d7f1c  push    r12
0x1800d7f1e  push    r13
0x1800d7f20  push    r14
0x1800d7f22  push    r15
0x1800d7f24  sub     rsp, 1A0h
0x1800d7f2b  movaps  [rsp+1D8h+var_48], xmm6
0x1800d7f33  mov     rax, cs:__security_cookie
0x1800d7f3a  xor     rax, rsp
0x1800d7f3d  mov     [rsp+1D8h+var_58], rax
0x1800d7f45  mov     rbx, r9
0x1800d7f48  mov     rdi, rdx
0x1800d7f4b  mov     r15, rcx
0x1800d7f4e  xor     r13d, r13d
0x1800d7f51  mov     rdx, [rdx+8]
0x1800d7f55  cmp     r8d, 800h
0x1800d7f5c  jnz     short loc_1800D7F93
0x1800d7f5e  test    rdx, rdx
0x1800d7f61  jz      short loc_1800D7F81
0x1800d7f63  mov     esi, 0FFFFFFFFh
0x1800d7f68  lock xadd [rdx+0Ch], esi
0x1800d7f6d  cmp     esi, 1
0x1800d7f70  jnz     short loc_1800D7F81
0x1800d7f72  mov     rax, [rdx]
0x1800d7f75  mov     rcx, rdx
0x1800d7f78  mov     rax, [rax+8]
0x1800d7f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7f81  mov     edx, 10h
0x1800d7f86  mov     rcx, rdi; Block
0x1800d7f89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d7f8e  jmp     loc_1800D95BF
0x1800d7f93  xorps   xmm6, xmm6
0x1800d7f96  movdqa  xmmword ptr [rsp+1D8h+var_168], xmm6
0x1800d7f9c  test    rdx, rdx
0x1800d7f9f  jz      short loc_1800D7FDD
0x1800d7fa1  mov     eax, [rdx+8]
0x1800d7fa4  test    eax, eax
0x1800d7fa6  jz      short loc_1800D7FDD
0x1800d7fa8  nop     dword ptr [rax+rax+00000000h]
0x1800d7fb0  lea     ecx, [rax+1]
0x1800d7fb3  lock cmpxchg [rdx+8], ecx
0x1800d7fb8  jz      short loc_1800D7FC4
0x1800d7fba  test    eax, eax
0x1800d7fbc  jnz     short loc_1800D7FB0
0x1800d7fbe  movdqa  xmm0, xmm6
0x1800d7fc2  jmp     short loc_1800D7FE0
0x1800d7fc4  mov     r14, [rdi]
0x1800d7fc7  mov     [rsp+1D8h+var_168], r14
0x1800d7fcc  mov     rdi, [rdi+8]
0x1800d7fd0  mov     [rsp+1D8h+var_168+8], rdi
0x1800d7fd5  movdqa  xmm6, xmmword ptr [rsp+1D8h+var_168]
0x1800d7fdb  jmp     short loc_1800D7FEF
0x1800d7fdd  xorps   xmm0, xmm0
0x1800d7fe0  psrldq  xmm0, 8
0x1800d7fe5  movq    r14, xmm6
0x1800d7fea  movq    rdi, xmm0
0x1800d7fef  test    r14, r14
0x1800d7ff2  jnz     short loc_1800D8007
0x1800d7ff4  test    rdi, rdi
0x1800d7ff7  jz      loc_1800D95BF
0x1800d7ffd  mov     esi, 0FFFFFFFFh
0x1800d8002  jmp     loc_1800D958C
0x1800d8007  cmp     r8d, 40000h
0x1800d800e  ja      loc_1800D8AD0
0x1800d8014  jz      loc_1800D8637
0x1800d801a  cmp     r8d, 10h
0x1800d801e  jz      loc_1800D861B
0x1800d8024  cmp     r8d, 4000h
0x1800d802b  jz      loc_1800D8439
0x1800d8031  mov     eax, 10000h
0x1800d8036  cmp     r8d, eax
0x1800d8039  jz      loc_1800D82F4
0x1800d803f  cmp     r8d, 20000h
0x1800d8046  jnz     loc_1800D8B00
0x1800d804c  mov     [rsp+1D8h+dwBufferLength], r13d
0x1800d8051  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x1800d8056  lea     rax, [rsp+1D8h+dwBufferLength]
0x1800d805b  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x1800d8060  xor     r9d, r9d; lpBuffer
0x1800d8063  xor     r8d, r8d; pwszName
0x1800d8066  mov     edx, 16h; dwInfoLevel
0x1800d806b  mov     rcx, r15; hRequest
0x1800d806e  call    cs:__imp_WinHttpQueryHeaders
0x1800d8074  xorps   xmm0, xmm0
0x1800d8077  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x1800d807d  mov     qword ptr [rsp+1D8h+var_178], r13
0x1800d8082  mov     edx, [rsp+1D8h+dwBufferLength]
0x1800d8086  lea     rcx, [rsp+1D8h+lpBuffer]
0x1800d808b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d8090  mov     rsi, [rsp+1D8h+lpBuffer]
0x1800d8095  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x1800d809a  lea     rax, [rsp+1D8h+dwBufferLength]
0x1800d809f  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x1800d80a4  mov     r9, rsi; lpBuffer
0x1800d80a7  xor     r8d, r8d; pwszName
0x1800d80aa  mov     edx, 16h; dwInfoLevel
0x1800d80af  mov     rcx, r15; hRequest
0x1800d80b2  call    cs:__imp_WinHttpQueryHeaders
0x1800d80b8  test    eax, eax
0x1800d80ba  jnz     loc_1800D8180
0x1800d80c0  call    cs:__imp_GetLastError
0x1800d80c6  mov     ebx, eax
0x1800d80c8  xorps   xmm0, xmm0
0x1800d80cb  movups  xmmword ptr [rsp+1D8h+Block], xmm0
0x1800d80d3  mov     qword ptr [rsp+1D8h+var_E0], r13
0x1800d80db  mov     qword ptr [rsp+1D8h+var_E0+8], r13
0x1800d80e3  mov     r8d, 13h
0x1800d80e9  lea     rdx, aWinhttpqueryhe; "WinHttpQueryHeaders"
0x1800d80f0  lea     rcx, [rsp+1D8h+Block]
0x1800d80f8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d80fd  nop
0x1800d80fe  lea     r8, [rsp+1D8h+Block]
0x1800d8106  mov     edx, ebx
0x1800d8108  lea     rcx, [rsp+1D8h+Src]; Src
0x1800d8110  call    web__http__client__details__build_error_msg
0x1800d8115  nop
0x1800d8116  mov     r8, rax
0x1800d8119  mov     edx, ebx
0x1800d811b  mov     rcx, r14
0x1800d811e  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d8123  nop
0x1800d8124  lea     rcx, [rsp+1D8h+Src]
0x1800d812c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d8131  nop
0x1800d8132  mov     rdx, qword ptr [rsp+1D8h+var_E0+8]
0x1800d813a  cmp     rdx, 0Fh
0x1800d813e  jbe     short loc_1800D817B
0x1800d8140  mov     rax, [rsp+1D8h+Block]
0x1800d8148  inc     rdx
0x1800d814b  cmp     rdx, 1000h
0x1800d8152  jb      short loc_1800D8172
0x1800d8154  mov     rcx, [rax-8]
0x1800d8158  sub     rax, rcx
0x1800d815b  sub     rax, 8
0x1800d815f  cmp     rax, 1Fh
0x1800d8163  ja      short loc_1800D816B
0x1800d8165  add     rdx, 27h ; '''
0x1800d8169  jmp     short loc_1800D8175
0x1800d816b  mov     ecx, 5
0x1800d8170  int     29h; Win8: RtlFailFast(ecx)
0x1800d8172  mov     rcx, rax; Block
0x1800d8175  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d817a  nop
0x1800d817b  jmp     loc_1800D857E
0x1800d8180  lea     r8, [r14+28h]
0x1800d8184  mov     rdx, rsi; this
0x1800d8187  mov     rcx, r15; hRequest
0x1800d818a  call    web__http__client__details__parse_winhttp_headers
0x1800d818f  mov     rax, [r14+28h]
0x1800d8193  movzx   ecx, word ptr [rax+88h]
0x1800d819a  mov     eax, 191h
0x1800d819f  cmp     cx, ax
0x1800d81a2  jz      short loc_1800D81AE
0x1800d81a4  mov     eax, 197h
0x1800d81a9  cmp     cx, ax
0x1800d81ac  jnz     short loc_1800D8221
0x1800d81ae  xor     r8d, r8d
0x1800d81b1  lea     rdx, [rsp+1D8h+var_168]
0x1800d81b6  mov     rcx, r15
0x1800d81b9  call    ?handle_authentication_failure@winhttp_client@details@client@http@web@@CA_NPEAXAEBV?$shared_ptr@Vwinhttp_request_context@details@client@http@web@@@std@@K@Z; web::http::client::details::winhttp_client::handle_authentication_failure(void *,std::shared_ptr<web::http::client::details::winhttp_request_context> const &,ulong)
0x1800d81be  test    al, al
0x1800d81c0  jz      short loc_1800D8217
0x1800d81c2  mov     rax, [rsp+1D8h+lpBuffer]
0x1800d81c7  test    rax, rax
0x1800d81ca  jz      loc_1800D8BDA
0x1800d81d0  mov     rdx, qword ptr [rsp+1D8h+var_178]
0x1800d81d5  sub     rdx, rax
0x1800d81d8  cmp     rdx, 1000h
0x1800d81df  jb      short loc_1800D81FC
0x1800d81e1  mov     rcx, [rax-8]
0x1800d81e5  sub     rax, rcx
0x1800d81e8  sub     rax, 8
0x1800d81ec  cmp     rax, 1Fh
0x1800d81f0  ja      loc_1800D8F77
0x1800d81f6  add     rdx, 27h ; '''
0x1800d81fa  jmp     short loc_1800D81FF
0x1800d81fc  mov     rcx, rax; Block
0x1800d81ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d8204  xorps   xmm0, xmm0
0x1800d8207  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x1800d820d  mov     qword ptr [rsp+1D8h+var_178], r13
0x1800d8212  jmp     loc_1800D8BDA
0x1800d8217  mov     rdi, [rsp+1D8h+var_168+8]
0x1800d821c  mov     r14, [rsp+1D8h+var_168]
0x1800d8221  mov     rcx, r14; this
0x1800d8224  call    ?handle_compression@request_context@details@client@http@web@@QEAA_NXZ; web::http::client::details::request_context::handle_compression(void)
0x1800d8229  test    al, al
0x1800d822b  jnz     short loc_1800D8232
0x1800d822d  jmp     loc_1800D857E
0x1800d8232  cmp     qword ptr [r14+60h], 0
0x1800d8237  jz      short loc_1800D82A4
0x1800d8239  mov     rcx, [r14+8]; this
0x1800d823d  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800d8242  cmp     byte ptr [rax+1A8h], 0
0x1800d8249  jnz     short loc_1800D82A4
0x1800d824b  mov     ecx, 10h; Size
0x1800d8250  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8255  mov     [rsp+1D8h+var_198], rax
0x1800d825a  test    rax, rax
0x1800d825d  jz      short loc_1800D826F
0x1800d825f  mov     [rax], r13
0x1800d8262  mov     dword ptr [rax+8], 1
0x1800d8269  mov     byte ptr [rax+0Ch], 0
0x1800d826d  jmp     short loc_1800D8272
0x1800d826f  mov     rax, r13
0x1800d8272  mov     [rsp+1D8h+var_198], rax
0x1800d8277  lea     rcx, [r14+140h]
0x1800d827e  lea     rdx, [rsp+1D8h+var_198]
0x1800d8283  call    ??$?4U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@$0A@@?$unique_ptr@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper> &&)
0x1800d8288  mov     rcx, [rsp+1D8h+var_198]; Block
0x1800d828d  test    rcx, rcx
0x1800d8290  jz      short loc_1800D829C
0x1800d8292  mov     edx, 10h
0x1800d8297  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d829c  mov     byte ptr [r14+133h], 1
0x1800d82a4  mov     rcx, r14; this
0x1800d82a7  call    ?complete_headers@request_context@details@client@http@web@@QEAAXXZ; web::http::client::details::request_context::complete_headers(void)
0x1800d82ac  mov     rcx, [r14+18h]
0x1800d82b0  add     rcx, 90h
0x1800d82b7  lea     rdx, ?HEAD@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::HEAD
0x1800d82be  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x1800d82c3  mov     rcx, r14; this
0x1800d82c6  test    al, al
0x1800d82c8  jz      short loc_1800D82E4
0x1800d82ca  xor     r8d, r8d; unsigned __int64
0x1800d82cd  xor     edx, edx; unsigned __int8 *
0x1800d82cf  call    ?allocate_request_space@winhttp_request_context@details@client@http@web@@QEAAXPEAE_K@Z; web::http::client::details::winhttp_request_context::allocate_request_space(uchar *,unsigned __int64)
0x1800d82d4  xor     edx, edx; unsigned __int64
0x1800d82d6  mov     rcx, r14; this
0x1800d82d9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800d82de  nop
0x1800d82df  jmp     loc_1800D857E
0x1800d82e4  mov     r8b, 1; bool
0x1800d82e7  xor     edx, edx; unsigned int
0x1800d82e9  call    ?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z; web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)
0x1800d82ee  nop
0x1800d82ef  jmp     loc_1800D857E
0x1800d82f4  mov     edx, [r9]
0x1800d82f7  lea     rcx, [rsp+1D8h+Src]; Src
0x1800d82ff  call    _anonymous_namespace___generate_security_failure_message
0x1800d8304  mov     rdx, rax
0x1800d8307  xorps   xmm0, xmm0
0x1800d830a  movups  [rsp+1D8h+var_A0], xmm0
0x1800d8312  lea     rcx, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800d8319  mov     [rsp+1D8h+var_A8], rcx
0x1800d8321  mov     [rsp+1D8h+var_90], r13d
0x1800d8329  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800d8330  mov     [rsp+1D8h+var_88], rcx
0x1800d8338  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x1800d8340  mov     qword ptr [rsp+1D8h+var_70], r13
0x1800d8348  mov     qword ptr [rsp+1D8h+var_70+8], r13
0x1800d8350  mov     rcx, [rax]
0x1800d8353  mov     [rsp+1D8h+var_80], rcx
0x1800d835b  mov     rcx, [rax+8]
0x1800d835f  mov     [rsp+1D8h+var_80+8], rcx
0x1800d8367  mov     rax, [rax+10h]
0x1800d836b  mov     qword ptr [rsp+1D8h+var_70], rax
0x1800d8373  mov     rax, [rdx+18h]
0x1800d8377  mov     qword ptr [rsp+1D8h+var_70+8], rax
0x1800d837f  mov     qword ptr [rdx+18h], 0Fh
0x1800d8387  mov     byte ptr [rdx], 0
0x1800d838a  mov     [rdx+10h], r13
0x1800d838e  mov     qword ptr [rdx+18h], 0Fh
0x1800d8396  mov     byte ptr [rdx], 0
0x1800d8399  lea     rdx, [rsp+1D8h+var_A8]
0x1800d83a1  mov     rcx, r14
0x1800d83a4  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800d83a9  nop
0x1800d83aa  mov     rdx, qword ptr [rsp+1D8h+var_70+8]
0x1800d83b2  cmp     rdx, 0Fh
0x1800d83b6  jbe     short loc_1800D83ED
0x1800d83b8  inc     rdx
0x1800d83bb  mov     rcx, [rsp+1D8h+var_80]
0x1800d83c3  cmp     rdx, 1000h
0x1800d83ca  jb      short loc_1800D83E8
0x1800d83cc  mov     rax, [rcx-8]
0x1800d83d0  sub     rcx, rax
0x1800d83d3  sub     rcx, 8
0x1800d83d7  cmp     rcx, 1Fh
0x1800d83db  ja      loc_1800D8F77
0x1800d83e1  add     rdx, 27h ; '''
0x1800d83e5  mov     rcx, rax; Block
0x1800d83e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d83ed  mov     qword ptr [rsp+1D8h+var_70], r13
0x1800d83f5  mov     qword ptr [rsp+1D8h+var_70+8], 0Fh
0x1800d8401  mov     byte ptr [rsp+1D8h+var_80], 0
0x1800d8409  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800d8410  mov     [rsp+1D8h+var_A8], rax
0x1800d8418  lea     rcx, [rsp+1D8h+var_A0]
0x1800d8420  call    _o___std_exception_destroy_0
0x1800d8425  nop
0x1800d8426  test    rdi, rdi
0x1800d8429  jz      loc_1800D95BF
0x1800d842f  mov     esi, 0FFFFFFFFh
0x1800d8434  jmp     loc_1800D958C
0x1800d8439  mov     rax, [r14+80h]
  ... truncated ...
```
