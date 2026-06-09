# web::http::client::details::winhttp_client::completion_callback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x180050120`
- end: `0x180051846`
- name: `?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z`
- size: `5926`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000eab2`
- `0x18000ec30`
- `0x180035460`
- `0x1800377f0`
- `0x180037dd0`
- `0x180037de0`
- `0x180037f20`
- `0x1800387f0`
- `0x180038ff0`
- `0x180044610`
- `0x180048890`
- `0x180049bb0`
- `0x180049cc0`
- `0x18004ca80`
- `0x18004e230`
- `0x18004e590`
- `0x18004f290`
- `0x18004fb80`
- `0x18004fbe0`
- `0x18004fde0`
- `0x180050080`
- `0x180050120`
- `0x180051ba0`
- `0x180052040`
- `0x180053700`
- `0x180054bc0`
- `0x1800551b0`
- `0x18005fd84`
- `0x18006511c`
- `0x1800709e4`
- `0x1800719ec`
- `0x180081190`
- `0x180099964`
- `0x18009a2e0`
- `0x1800a64d8`
- `0x1800a7ebc`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005113b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005113b`
- `WINHTTP!WinHttpReceiveResponse` at `0x180050e95`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005112d`
- `WINHTTP!WinHttpReceiveResponse` at `0x180050e95`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005112d`
- `WINHTTP!WinHttpReadData` at `0x180050935`
- `WINHTTP!WinHttpReadData` at `0x180050935`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005027e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800502c2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180050636`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005067a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005027e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800502c2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180050636`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005067a`

## string_xrefs

- `0x18005096b`: `WinHttpReadData`
- `0x180050ba7`: `Received incomplete compressed stream`
- `0x18005136f`: `Received incomplete compressed stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  __int16 v19; // cx
  const struct std::nothrow_t *v20; // rdx
  void *v21; // rcx
  _QWORD *v22; // rax
  __int64 security_failure_message; // rax
  __int64 v24; // rax
  web::http::details *v25; // rbx
  DWORD v26; // ebx
  __int64 v27; // rax
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rcx
  __int64 v30; // rdx
  int (__fastcall *v31)(_QWORD, _QWORD); // rax
  unsigned __int64 v32; // rsi
  void *v33; // rbx
  __int64 v34; // rax
  DWORD v35; // ebx
  __int64 v36; // r8
  const struct std::nothrow_t *v37; // rdx
  void *v38; // rcx
  void *v39; // rcx
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  volatile signed __int32 *v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  volatile signed __int32 *v49; // rbx
  bool v50; // r12
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rcx
  std::_Ref_count_base *v54; // rbx
  int v55; // eax
  DWORD v56; // ebx
  __int64 v57; // rax
  void *v58; // rcx
  unsigned int v59; // esi
  __int64 v60; // rax
  void *v61; // rcx
  __int64 v62; // r12
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rcx
  volatile signed __int32 *v66; // rbx
  __int64 readbuffer; // rax
  __int64 v68; // rdx
  int v69; // eax
  DWORD LastError; // ebx
  __int64 v71; // rax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rcx
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // rax
  __int64 v77; // rax
  volatile signed __int32 *v78; // r14
  volatile signed __int32 *v79; // r14
  volatile signed __int32 *v80; // r14
  __int64 v81; // r8
  volatile signed __int32 *v82; // r14
  volatile signed __int32 *v83; // r14
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-1A8h] BYREF
  void *v89[2]; // [rsp+40h] [rbp-198h] BYREF
  LPVOID lpBuffer[2]; // [rsp+50h] [rbp-188h] BYREF
  __int128 v91; // [rsp+60h] [rbp-178h]
  std::_Ref_count_base *v92[2]; // [rsp+70h] [rbp-168h] BYREF
  __int64 v93; // [rsp+80h] [rbp-158h]
  std::_Ref_count_base *v94; // [rsp+88h] [rbp-150h]
  _BYTE v95[8]; // [rsp+90h] [rbp-148h] BYREF
  volatile signed __int32 *v96; // [rsp+98h] [rbp-140h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v98[24]; // [rsp+B8h] [rbp-120h] BYREF
  _BYTE v99[24]; // [rsp+D0h] [rbp-108h] BYREF
  void *v100[2]; // [rsp+E8h] [rbp-F0h] BYREF
  __int128 v101; // [rsp+F8h] [rbp-E0h]
  void *Src[2]; // [rsp+108h] [rbp-D0h] BYREF
  volatile signed __int32 *v103; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v104; // [rsp+120h] [rbp-B8h]
  void **v105; // [rsp+130h] [rbp-A8h] BYREF
  __int128 v106; // [rsp+138h] [rbp-A0h] BYREF
  int v107; // [rsp+148h] [rbp-90h]
  void ***v108; // [rsp+150h] [rbp-88h]
  void *v109[2]; // [rsp+158h] [rbp-80h] BYREF
  __int128 v110; // [rsp+168h] [rbp-70h]

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
    operator delete(dwContext, (const struct std::nothrow_t *)0x10);
    return;
  }
  si128 = 0;
  *(_OWORD *)v92 = 0;
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
    v92[0] = *dwContext;
    v13 = (volatile signed __int32 *)dwContext[1];
    v92[1] = (std::_Ref_count_base *)v13;
    si128 = _mm_load_si128((const __m128i *)v92);
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
LABEL_249:
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    return;
  }
  if ( dwInternetStatus > 0x40000 )
  {
    if ( dwInternetStatus != 0x80000 )
    {
      if ( dwInternetStatus == 0x100000 )
      {
        v62 = (unsigned int)*lpvStatusInformation;
        if ( (_DWORD)v62 )
        {
          v63 = *((_QWORD *)v12 + 3);
          v64 = *(_QWORD *)(v63 + 720);
          if ( v64 )
            _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
          v65 = *(_QWORD *)(v63 + 712);
          v93 = v65;
          v66 = *(volatile signed __int32 **)(v63 + 720);
          v94 = (std::_Ref_count_base *)v66;
          if ( v65 )
          {
            try
            {
              *((_QWORD *)v12 + 7) += v62;
              std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v65, 0);
            }
            catch ( ... )
            {
              v85 = std::current_exception(v89);
              web::http::client::details::request_context::report_exception(v92[0], v85);
              goto LABEL_148;
            }
          }
          if ( v66 )
          {
            if ( _InterlockedExchangeAdd(v66 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
              if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
            }
          }
        }
        if ( *((_QWORD *)v12 + 27) )
        {
          readbuffer = web::http::client::details::winhttp_request_context::_get_readbuffer(v12, v100);
          v68 = *((_QWORD *)v12 + 27);
          if ( !v68 )
            v68 = *((_QWORD *)v12 + 28);
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)readbuffer + 248LL))(readbuffer, v68, v62);
          Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v100);
        }
        v69 = *((_DWORD *)v12 + 34);
        if ( v69 == 2 )
        {
LABEL_155:
          web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(v12);
          goto LABEL_248;
        }
        if ( v69 == 1 )
        {
LABEL_157:
          web::http::client::details::winhttp_client::_multiple_segment_write_data(v12);
          goto LABEL_248;
        }
        if ( WinHttpReceiveResponse(hInternet, 0) )
          goto LABEL_248;
        LastError = GetLastError();
        *(_OWORD *)v100 = 0;
        v89[0] = (void *)31;
        v100[0] = (void *)std::string::_Allocate_for_capacity<0>(v100, v89);
        *(_QWORD *)&v101 = 22;
        *((void **)&v101 + 1) = v89[0];
        strcpy((char *)v100[0], "WinHttpReceiveResponse");
        v71 = web::http::client::details::build_error_msg(Src);
        web::http::client::details::request_context::report_error(v12, LastError, v71);
        std::tuple<char const *,std::string>::~tuple<char const *,std::string>(Src);
LABEL_160:
        if ( *((_QWORD *)&v101 + 1) > 0xFu )
        {
          if ( (unsigned __int64)(*((_QWORD *)&v101 + 1) + 1LL) < 0x1000 )
          {
            operator delete(v100[0], (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 1LL));
          }
          else
          {
            v58 = (void *)*((_QWORD *)v100[0] - 1);
            if ( (unsigned __int64)((char *)v100[0] - (char *)v58 - 8) > 0x1F )
              goto LABEL_189;
            operator delete(v58, (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 40LL));
          }
        }
LABEL_248:
        if ( !v13 )
          return;
        goto LABEL_249;
      }
      if ( dwInternetStatus != 0x200000 )
      {
        if ( dwInternetStatus != 0x400000 )
          goto LABEL_55;
        v46 = *((_QWORD *)v12 + 3);
        v47 = *(_QWORD *)(v46 + 56);
        if ( v47 )
          _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
        v48 = *(_QWORD *)(v46 + 48);
        v49 = *(volatile signed __int32 **)(v46 + 56);
        v50 = !v48 || !*(_QWORD *)(v48 + 8);
        if ( v49 )
        {
          if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
        if ( v50 )
        {
          v51 = *((_QWORD *)v12 + 3);
          v52 = *(_QWORD *)(v51 + 720);
          if ( v52 )
            _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
          v53 = *(_QWORD *)(v51 + 712);
          v93 = v53;
          v54 = *(std::_Ref_count_base **)(v51 + 720);
          v94 = v54;
          if ( v53 )
          {
            try
            {
              std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v53, 0);
            }
            catch ( ... )
            {
              v84 = std::current_exception(v89);
              web::http::client::details::request_context::report_exception(v92[0], v84);
              goto LABEL_148;
            }
          }
          if ( v54 )
            std::_Ref_count_base::_Decref(v54);
        }
        v55 = *((_DWORD *)v12 + 34);
        if ( v55 == 2 )
          goto LABEL_155;
        if ( v55 == 1 )
          goto LABEL_157;
        if ( WinHttpReceiveResponse(hInternet, 0) )
          goto LABEL_248;
        v56 = GetLastError();
        *(_OWORD *)v100 = 0;
        v101 = 0u;
        std::string::_Construct<1,char const *>(v100, "WinHttpReceiveResponse", 22);
        v57 = web::http::client::details::build_error_msg(Src);
        web::http::client::details::request_context::report_error(v12, v56, v57);
        std::tuple<char const *,std::string>::~tuple<char const *,std::string>(Src);
        goto LABEL_160;
      }
      v59 = lpvStatusInformation[2];
      if ( v59 != 12032 )
      {
LABEL_168:
        v60 = web::http::client::details::build_error_msg_0(Src);
        web::http::client::details::request_context::report_error(v12, v59, v60);
        if ( v104 > 0xF )
        {
          if ( v104 + 1 < 0x1000 )
          {
            operator delete(Src[0], (const struct std::nothrow_t *)(v104 + 1));
          }
          else
          {
            v61 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v61 - 8) > 0x1F )
              goto LABEL_189;
            operator delete(v61, (const struct std::nothrow_t *)(v104 + 40));
          }
        }
        goto LABEL_55;
      }
      if ( !(unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                               hInternet,
                               v92,
                               12032) )
      {
        v13 = (volatile signed __int32 *)v92[1];
        v12 = v92[0];
        goto LABEL_168;
      }
LABEL_150:
      if ( v92[1] )
        std::_Ref_count_base::_Decref(v92[1]);
      return;
    }
    v72 = *((_QWORD *)v12 + 3);
    v73 = *(_QWORD *)(v72 + 720);
    if ( v73 )
      _InterlockedIncrement((volatile signed __int32 *)(v73 + 8));
    v93 = *(_QWORD *)(v72 + 712);
    v74 = v93;
    v45 = *(volatile signed __int32 **)(v72 + 720);
    v94 = (std::_Ref_count_base *)v45;
    *((_QWORD *)v12 + 8) += dwStatusInformationLength;
    if ( v74 )
    {
      try
      {
        std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v74, 1);
      }
      catch ( ... )
      {
        v87 = std::current_exception(v89);
        web::http::client::details::request_context::report_exception(v92[0], v87);
LABEL_148:
        if ( v94 )
          std::_Ref_count_base::_Decref(v94);
        goto LABEL_150;
      }
    }
    if ( !dwStatusInformationLength )
    {
      if ( *((_QWORD *)v12 + 12) )
      {
        if ( *((_BYTE *)v12 + 307) )
        {
          lpBuffer[1] = 0;
          lpBuffer[0] = operator new(0x30u);
          *(_QWORD *)&v91 = 42;
          *((_QWORD *)&v91 + 1) = 47;
          strcpy((char *)lpBuffer[0], "Chunked response stream ended unexpectedly");
          v106 = 0;
          v105 = &web::http::http_exception::`vftable';
          v107 = 0;
          v108 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
          *(_OWORD *)v109 = *(_OWORD *)lpBuffer;
          v110 = v91;
          web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v105);
          std::tuple<char const *,std::string>::~tuple<char const *,std::string>(v109);
          v105 = &std::exception::`vftable';
          o___std_exception_destroy_0(&v106);
          goto LABEL_244;
        }
        if ( *((_BYTE *)v12 + 305) && !*((_BYTE *)v12 + 306) )
        {
          *(_OWORD *)lpBuffer = 0;
          v91 = 0u;
          std::string::_Construct<1,char const *>(lpBuffer, "Received incomplete compressed stream", 37);
          v106 = 0;
          v105 = &web::http::http_exception::`vftable';
          v107 = 0;
          v108 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
          *(_OWORD *)v109 = *(_OWORD *)lpBuffer;
          v110 = v91;
          web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v105);
          std::tuple<char const *,std::string>::~tuple<char const *,std::string>(v109);
          v105 = &std::exception::`vftable';
          o___std_exception_destroy_0(&v106);
          if ( v45 )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v45);
          if ( v13 )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
          return;
        }
      }
      web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
LABEL_244:
      if ( !v45 )
        goto LABEL_248;
      goto LABEL_245;
    }
    web::http::client::details::request_context::_get_writebuffer(v12, v100);
    if ( *((_QWORD *)v12 + 12) )
    {
      v75 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                             + 1))
            + 53);
      if ( !v75 )
        v75 = 0x10000;
      v76 = dwStatusInformationLength;
      if ( dwStatusInformationLength < v75 )
        v76 = v75;
      *((_QWORD *)v12 + 36) = dwStatusInformationLength;
      *((_QWORD *)v12 + 39) = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      *(__m128i *)v89 = si128;
      *(_OWORD *)Src = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[0] = v12;
      Src[1] = (void *)v13;
      v103 = (volatile signed __int32 *)v76;
      v104 = v76;
      v77 = ____do_while_V_lambda_2___JJ___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__N_details_pplx__YA_AV__task__N_1_V_lambda_2___JJ___completion_callback_winhttp_client_0client_http_web__CAXPEAX_KK0K_Z__Z(
              (__int64)lpBuffer,
              (__int64 *)Src);
      ___then_V_lambda_3___JJ___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__N_pplx__QEBA_AV__task_X_1___QEAV_lambda_3___JJ___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v77,
        v95,
        v89);
      v78 = v96;
      if ( v96 )
      {
        if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
          if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
        }
      }
      v79 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
          if ( _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
        }
      }
      v80 = (volatile signed __int32 *)v89[1];
    }
    else
    {
      if ( *((_QWORD *)v12 + 27) )
      {
        if ( !v100[1] )
        {
          std::invalid_argument::invalid_argument((std::invalid_argument *)v98, "Invalid streambuf object");
          throw (std::invalid_argument *)v98;
        }
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v100[1] + 232LL))(v100[1], dwStatusInformationLength);
        web::http::client::details::winhttp_client::read_next_response_chunk(v12, dwStatusInformationLength, 0);
        goto LABEL_243;
      }
      Src[0] = hInternet;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[1] = v12;
      v103 = v13;
      LODWORD(v104) = dwStatusInformationLength;
      v81 = *((_QWORD *)v12 + 27);
      if ( !v81 )
        v81 = *((_QWORD *)v12 + 28);
      if ( !v100[1] )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)v99, "Invalid streambuf object");
        throw (std::invalid_argument *)v99;
      }
      (*(void (__fastcall **)(void *, void **, __int64, _QWORD))(*(_QWORD *)v100[1] + 112LL))(
        v100[1],
        v89,
        v81,
        dwStatusInformationLength);
      ___then_V_lambda_4___KA___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_4___KA___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v89,
        lpBuffer,
        Src);
      v82 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
          if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
        }
      }
      v83 = (volatile signed __int32 *)v89[1];
      if ( v89[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v89[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
          if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
        }
      }
      v80 = v103;
    }
    if ( v80 )
    {
      if ( _InterlockedExchangeAdd(v80 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
        if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
      }
    }
LABEL_243:
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v100);
    goto LABEL_244;
  }
  if ( dwInternetStatus != 0x40000 )
  {
    if ( dwInternetStatus == 16 )
    {
      v30 = *((_QWORD *)v12 + 3);
      v31 = *(int (__fastcall **)(_QWORD, _QWORD))(v30 + 776);
      if ( v31 )
      {
        if ( v31(*((_QWORD *)v12 + 13), *(_QWORD *)(v30 + 784)) < 0 )
        {
          web::http::client::details::winhttp_request_context::cleanup(v12);
          if ( !v13 )
            return;
          goto LABEL_249;
        }
      }
      else
      {
        web::http::client::details::winhttp_request_context::on_send_request_validate_cn(v12);
      }
      if ( !v13 )
        return;
      goto LABEL_249;
    }
    if ( dwInternetStatus == 0x4000 )
    {
      v24 = *((_QWORD *)v12 + 16);
      if ( v24 )
      {
        *((_QWORD *)v12 + 16) = v24 - 1;
        if ( !v13 )
          return;
        goto LABEL_249;
      }
      dwBufferLength[0] = 0;
      WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
      *(_OWORD *)lpBuffer = 0;
      *(_QWORD *)&v91 = 0;
      std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
      v25 = (web::http::details *)lpBuffer[0];
      if ( WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
      {
        web::http::client::details::parse_winhttp_headers(hInternet, v25);
        web::http::client::details::request_context::complete_headers(v12);
        web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
        web::http::client::details::request_context::complete_request(v12, 0);
        web::http::client::details::winhttp_request_context::cleanup(v12);
        goto LABEL_68;
      }
      v26 = GetLastError();
      *(_OWORD *)v100 = 0;
      v89[0] = (void *)31;
      v100[0] = (void *)std::string::_Allocate_for_capacity<0>(v100, v89);
      *(_QWORD *)&v101 = 19;
      *((void **)&v101 + 1) = v89[0];
      strcpy((char *)v100[0], "WinHttpQueryHeaders");
      v27 = web::http::client::details::build_error_msg(Src);
      web::http::client::details::request_context::report_error(v12, v26, v27);
      std::tuple<char const *,std::string>::~tuple<char const *,std::string>(Src);
      if ( *((_QWORD *)&v101 + 1) > 0xFu )
      {
        v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 1LL);
        if ( (unsigned __int64)(*((_QWORD *)&v101 + 1) + 1LL) < 0x1000 )
        {
          v18 = v100[0];
        }
        else
        {
          v18 = (void *)*((_QWORD *)v100[0] - 1);
          if ( (unsigned __int64)((char *)v100[0] - (char *)v18 - 8) > 0x1F )
            __fastfail(5u);
          v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 40LL);
        }
        goto LABEL_67;
      }
LABEL_68:
      if ( !lpBuffer[0] )
        goto LABEL_74;
      v28 = (const struct std::nothrow_t *)(v91 - (unsigned __int64)lpBuffer[0]);
      if ( (unsigned __int64)v91 - (unsigned __int64)lpBuffer[0] < 0x1000 )
      {
        v29 = lpBuffer[0];
        goto LABEL_73;
      }
      v29 = (void *)*((_QWORD *)lpBuffer[0] - 1);
      if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v29 - 8) <= 0x1F )
      {
        v28 = (const struct std::nothrow_t *)((char *)v28 + 39);
LABEL_73:
        operator delete(v29, v28);
        *(_OWORD *)lpBuffer = 0;
        *(_QWORD *)&v91 = 0;
LABEL_74:
        if ( v13 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
        return;
      }
LABEL_189:
      __fastfail(5u);
    }
    if ( dwInternetStatus != 0x10000 )
    {
      if ( dwInternetStatus == 0x20000 )
      {
        dwBufferLength[0] = 0;
        WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
        *(_OWORD *)lpBuffer = 0;
        *(_QWORD *)&v91 = 0;
        std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
        v14 = (web::http::details *)lpBuffer[0];
        if ( !WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
        {
          v15 = GetLastError();
          *(_OWORD *)v100 = 0;
          v101 = 0u;
          std::string::_Construct<1,char const *>(v100, "WinHttpQueryHeaders", 19);
          v16 = web::http::client::details::build_error_msg(Src);
          web::http::client::details::request_context::report_error(v12, v15, v16);
          std::tuple<char const *,std::string>::~tuple<char const *,std::string>(Src);
          if ( *((_QWORD *)&v101 + 1) > 0xFu )
          {
            v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 1LL);
            if ( (unsigned __int64)(*((_QWORD *)&v101 + 1) + 1LL) < 0x1000 )
            {
              v18 = v100[0];
            }
            else
            {
              v18 = (void *)*((_QWORD *)v100[0] - 1);
              if ( (unsigned __int64)((char *)v100[0] - (char *)v18 - 8) > 0x1F )
                __fastfail(5u);
              v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 40LL);
            }
LABEL_67:
            operator delete(v18, v17);
            goto LABEL_68;
          }
          goto LABEL_68;
        }
        web::http::client::details::parse_winhttp_headers(hInternet, v14);
        v19 = *(_WORD *)(*((_QWORD *)v12 + 5) + 136LL);
        if ( v19 == 401 || v19 == 407 )
        {
          if ( (unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                                  hInternet,
                                  v92,
                                  0) )
          {
            if ( lpBuffer[0] )
            {
              v20 = (const struct std::nothrow_t *)(v91 - (unsigned __int64)lpBuffer[0]);
              if ( (unsigned __int64)v91 - (unsigned __int64)lpBuffer[0] < 0x1000 )
              {
                v21 = lpBuffer[0];
              }
              else
              {
                v21 = (void *)*((_QWORD *)lpBuffer[0] - 1);
                if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v21 - 8) > 0x1F )
                  goto LABEL_189;
                v20 = (const struct std::nothrow_t *)((char *)v20 + 39);
              }
              operator delete(v21, v20);
              *(_OWORD *)lpBuffer = 0;
              *(_QWORD *)&v91 = 0;
            }
            goto LABEL_150;
          }
          v13 = (volatile signed __int32 *)v92[1];
          v12 = v92[0];
        }
        if ( web::http::client::details::request_context::handle_compression(v12) )
        {
          if ( *((_QWORD *)v12 + 12)
            && !*((_BYTE *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                                + 1))
                + 432) )
          {
            v22 = operator new(0x10u);
            v89[0] = v22;
            if ( v22 )
            {
              *v22 = 0;
              *((_DWORD *)v22 + 2) = 1;
              *((_BYTE *)v22 + 12) = 0;
            }
            else
            {
              v22 = 0;
            }
            v89[0] = v22;
            std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(
              (void **)v12 + 40,
              v89);
            if ( v89[0] )
              operator delete(v89[0], (const struct std::nothrow_t *)0x10);
            *((_BYTE *)v12 + 307) = 1;
          }
          web::http::client::details::request_context::complete_headers(v12);
          if ( (unsigned __int8)std::operator==<unsigned short>(*((_QWORD *)v12 + 3) + 144LL, &web::http::methods::HEAD) )
          {
            web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
            web::http::client::details::request_context::complete_request(v12, 0);
          }
          else
          {
            web::http::client::details::winhttp_client::read_next_response_chunk(v12, 0, 1);
          }
        }
        goto LABEL_68;
      }
LABEL_55:
      if ( !v13 )
        return;
      goto LABEL_249;
    }
    security_failure_message = anonymous_namespace_::generate_security_failure_message(Src);
    v106 = 0;
    v105 = &web::http::http_exception::`vftable';
    v107 = 0;
    v108 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v109 = 0;
    v110 = 0u;
    *(_OWORD *)v109 = *(_OWORD *)security_failure_message;
    v110 = *(_OWORD *)(security_failure_message + 16);
    *(_QWORD *)(security_failure_message + 24) = 15;
    *(_BYTE *)security_failure_message = 0;
    *(_QWORD *)(security_failure_message + 16) = 0;
    *(_QWORD *)(security_failure_message + 24) = 15;
    *(_BYTE *)security_failure_message = 0;
    web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v105);
LABEL_54:
    std::tuple<char const *,std::string>::~tuple<char const *,std::string>(v109);
    v105 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v106);
    goto LABEL_55;
  }
  v32 = (unsigned int)*lpvStatusInformation;
  if ( (_DWORD)v32 )
  {
    if ( *((_QWORD *)v12 + 12) )
    {
      if ( *((_QWORD *)v12 + 34) - *((_QWORD *)v12 + 32) < v32 )
        std::vector<unsigned char>::reserve((char *)v12 + 256, (unsigned int)v32);
      v33 = (void *)*((_QWORD *)v12 + 32);
    }
    else
    {
      web::http::client::details::request_context::_get_writebuffer(v12, v100);
      if ( !v100[1] )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
        throw (std::invalid_argument *)pExceptionObject;
      }
      v34 = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)v100[1] + 224LL))(v100[1], v32);
      if ( v34 )
      {
        *((_QWORD *)v12 + 31) = v32;
      }
      else
      {
        if ( v32 > *((_QWORD *)v12 + 29) - *((_QWORD *)v12 + 28) )
          std::vector<unsigned char>::resize((char *)v12 + 224, v32);
        v34 = 0;
      }
      *((_QWORD *)v12 + 27) = v34;
      v33 = (void *)v34;
      if ( !v34 )
        v33 = (void *)*((_QWORD *)v12 + 28);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v100);
    }
    if ( !WinHttpReadData(hInternet, v33, v32, 0) )
    {
      v35 = GetLastError();
      *(_QWORD *)&v101 = 15;
      *((_QWORD *)&v101 + 1) = 15;
      qmemcpy(v100, "WinHttpReadDat", 14);
      HIWORD(v100[1]) = (unsigned __int8)aWinhttpreaddat_0[14];
      v36 = web::http::client::details::build_error_msg(Src);
      web::http::client::details::request_context::report_error(v12, v35, v36);
      if ( v104 > 0xF )
      {
        v37 = (const struct std::nothrow_t *)(v104 + 1);
        if ( v104 + 1 < 0x1000 )
        {
          v38 = Src[0];
        }
        else
        {
          v38 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v38 - 8) > 0x1F )
            __fastfail(5u);
          v37 = (const struct std::nothrow_t *)(v104 + 40);
        }
        operator delete(v38, v37);
      }
      v103 = 0;
      v104 = 15;
      LOBYTE(Src[0]) = 0;
      if ( *((_QWORD *)&v101 + 1) > 0xFu )
      {
        if ( (unsigned __int64)(*((_QWORD *)&v101 + 1) + 1LL) < 0x1000 )
        {
          operator delete(v100[0], (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 1LL));
        }
        else
        {
          v39 = (void *)*((_QWORD *)v100[0] - 1);
          if ( (unsigned __int64)((char *)v100[0] - (char *)v39 - 8) > 0x1F )
            goto LABEL_189;
          operator delete(v39, (const struct std::nothrow_t *)(*((_QWORD *)&v101 + 1) + 40LL));
        }
      }
    }
    goto LABEL_248;
  }
  if ( !*((_QWORD *)v12 + 12) )
    goto LABEL_124;
  if ( *((_BYTE *)v12 + 307) )
  {
    v100[1] = 0;
    v100[0] = operator new(0x30u);
    *(_QWORD *)&v101 = 42;
    *((_QWORD *)&v101 + 1) = 47;
    strcpy((char *)v100[0], "Chunked response stream ended unexpectedly");
    v106 = 0;
    v105 = &web::http::http_exception::`vftable';
    v107 = 0;
    v108 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v109 = *(_OWORD *)v100;
    v110 = v101;
    web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v105);
    goto LABEL_54;
  }
  if ( !*((_BYTE *)v12 + 305) || *((_BYTE *)v12 + 306) )
  {
LABEL_124:
    v42 = *((_QWORD *)v12 + 3);
    v43 = *(_QWORD *)(v42 + 720);
    if ( v43 )
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
    v44 = *(_QWORD *)(v42 + 712);
    v93 = v44;
    v45 = *(volatile signed __int32 **)(v42 + 720);
    v94 = (std::_Ref_count_base *)v45;
    if ( v44 )
    {
      try
      {
        std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v44, 1);
      }
      catch ( ... )
      {
        v86 = std::current_exception(v89);
        web::http::client::details::request_context::report_exception(v92[0], v86);
        goto LABEL_148;
      }
    }
    web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
    if ( !v45 )
      goto LABEL_248;
LABEL_245:
    if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
      if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
    }
    goto LABEL_248;
  }
  *(_OWORD *)v100 = 0;
  v101 = 0u;
  std::string::_Construct<1,char const *>(v100, "Received incomplete compressed stream", 37);
  v106 = 0;
  v105 = &web::http::http_exception::`vftable';
  v107 = 0;
  v108 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v109[0] = v100[0];
  v109[1] = v100[1];
  v110 = v101;
  web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v105);
  if ( *((_QWORD *)&v110 + 1) > 0xFu )
  {
    v40 = (const struct std::nothrow_t *)(*((_QWORD *)&v110 + 1) + 1LL);
    if ( (unsigned __int64)(*((_QWORD *)&v110 + 1) + 1LL) < 0x1000 )
    {
      v41 = v109[0];
    }
    else
    {
      v41 = (void *)*((_QWORD *)v109[0] - 1);
      if ( (unsigned __int64)((char *)v109[0] - (char *)v41 - 8) > 0x1F )
        goto LABEL_189;
      v40 = (const struct std::nothrow_t *)(*((_QWORD *)&v110 + 1) + 40LL);
    }
    operator delete(v41, v40);
  }
  *(_QWORD *)&v110 = 0;
  *((_QWORD *)&v110 + 1) = 15;
  LOBYTE(v109[0]) = 0;
  v105 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v106);
  if ( v13 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
}

```

## disassembly

```asm
0x180050120  test    rdx, rdx
0x180050123  jz      locret_1800517CA
0x180050129  push    rbx
0x18005012a  push    rsi
0x18005012b  push    rdi
0x18005012c  push    r12
0x18005012e  push    r13
0x180050130  push    r14
0x180050132  push    r15
0x180050134  sub     rsp, 1A0h
0x18005013b  movaps  [rsp+1D8h+var_48], xmm6
0x180050143  mov     rax, cs:__security_cookie
0x18005014a  xor     rax, rsp
0x18005014d  mov     [rsp+1D8h+var_58], rax
0x180050155  mov     rbx, r9
0x180050158  mov     rdi, rdx
0x18005015b  mov     r15, rcx
0x18005015e  xor     r13d, r13d
0x180050161  mov     rdx, [rdx+8]
0x180050165  cmp     r8d, 800h
0x18005016c  jnz     short loc_1800501A3
0x18005016e  test    rdx, rdx
0x180050171  jz      short loc_180050191
0x180050173  mov     esi, 0FFFFFFFFh
0x180050178  lock xadd [rdx+0Ch], esi
0x18005017d  cmp     esi, 1
0x180050180  jnz     short loc_180050191
0x180050182  mov     rax, [rdx]
0x180050185  mov     rcx, rdx
0x180050188  mov     rax, [rax+8]
0x18005018c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050191  mov     edx, 10h; struct std::nothrow_t *
0x180050196  mov     rcx, rdi; void *
0x180050199  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005019e  jmp     loc_1800517A0
0x1800501a3  xorps   xmm6, xmm6
0x1800501a6  movdqa  xmmword ptr [rsp+1D8h+var_168], xmm6
0x1800501ac  test    rdx, rdx
0x1800501af  jz      short loc_1800501ED
0x1800501b1  mov     eax, [rdx+8]
0x1800501b4  test    eax, eax
0x1800501b6  jz      short loc_1800501ED
0x1800501b8  nop     dword ptr [rax+rax+00000000h]
0x1800501c0  lea     ecx, [rax+1]
0x1800501c3  lock cmpxchg [rdx+8], ecx
0x1800501c8  jz      short loc_1800501D4
0x1800501ca  test    eax, eax
0x1800501cc  jnz     short loc_1800501C0
0x1800501ce  movdqa  xmm0, xmm6
0x1800501d2  jmp     short loc_1800501F0
0x1800501d4  mov     r14, [rdi]
0x1800501d7  mov     [rsp+1D8h+var_168], r14
0x1800501dc  mov     rdi, [rdi+8]
0x1800501e0  mov     [rsp+1D8h+var_168+8], rdi
0x1800501e5  movdqa  xmm6, xmmword ptr [rsp+1D8h+var_168]
0x1800501eb  jmp     short loc_1800501FF
0x1800501ed  xorps   xmm0, xmm0
0x1800501f0  psrldq  xmm0, 8
0x1800501f5  movq    r14, xmm6
0x1800501fa  movq    rdi, xmm0
0x1800501ff  test    r14, r14
0x180050202  jnz     short loc_180050217
0x180050204  test    rdi, rdi
0x180050207  jz      loc_1800517A0
0x18005020d  mov     esi, 0FFFFFFFFh
0x180050212  jmp     loc_18005176D
0x180050217  cmp     r8d, 40000h
0x18005021e  ja      loc_180050D45
0x180050224  jz      loc_180050864
0x18005022a  cmp     r8d, 10h
0x18005022e  jz      loc_180050808
0x180050234  cmp     r8d, 4000h
0x18005023b  jz      loc_1800505EB
0x180050241  mov     eax, 10000h
0x180050246  cmp     r8d, eax
0x180050249  jz      loc_180050504
0x18005024f  cmp     r8d, 20000h
0x180050256  jnz     loc_1800505D8
0x18005025c  mov     [rsp+1D8h+dwBufferLength], r13d
0x180050261  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x180050266  lea     rax, [rsp+1D8h+dwBufferLength]
0x18005026b  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180050270  xor     r9d, r9d; lpBuffer
0x180050273  xor     r8d, r8d; pwszName
0x180050276  mov     edx, 16h; dwInfoLevel
0x18005027b  mov     rcx, r15; hRequest
0x18005027e  call    cs:__imp_WinHttpQueryHeaders
0x180050284  xorps   xmm0, xmm0
0x180050287  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18005028d  mov     qword ptr [rsp+1D8h+var_178], r13
0x180050292  mov     edx, [rsp+1D8h+dwBufferLength]
0x180050296  lea     rcx, [rsp+1D8h+lpBuffer]
0x18005029b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800502a0  mov     rsi, [rsp+1D8h+lpBuffer]
0x1800502a5  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x1800502aa  lea     rax, [rsp+1D8h+dwBufferLength]
0x1800502af  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x1800502b4  mov     r9, rsi; lpBuffer
0x1800502b7  xor     r8d, r8d; pwszName
0x1800502ba  mov     edx, 16h; dwInfoLevel
0x1800502bf  mov     rcx, r15; hRequest
0x1800502c2  call    cs:__imp_WinHttpQueryHeaders
0x1800502c8  test    eax, eax
0x1800502ca  jnz     loc_180050390
0x1800502d0  call    cs:__imp_GetLastError
0x1800502d6  mov     ebx, eax
0x1800502d8  xorps   xmm0, xmm0
0x1800502db  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x1800502e3  mov     qword ptr [rsp+1D8h+var_E0], r13
0x1800502eb  mov     qword ptr [rsp+1D8h+var_E0+8], r13
0x1800502f3  mov     r8d, 13h
0x1800502f9  lea     rdx, aWinhttpqueryhe_0; "WinHttpQueryHeaders"
0x180050300  lea     rcx, [rsp+1D8h+var_F0]
0x180050308  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005030d  nop
0x18005030e  lea     r8, [rsp+1D8h+var_F0]
0x180050316  mov     edx, ebx
0x180050318  lea     rcx, [rsp+1D8h+Src]; Src
0x180050320  call    web__http__client__details__build_error_msg
0x180050325  nop
0x180050326  mov     r8, rax
0x180050329  mov     edx, ebx
0x18005032b  mov     rcx, r14
0x18005032e  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180050333  nop
0x180050334  lea     rcx, [rsp+1D8h+Src]
0x18005033c  call    ??1?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::tuple<char const *,std::string>::~tuple<char const *,std::string>(void)
0x180050341  nop
0x180050342  mov     rdx, qword ptr [rsp+1D8h+var_E0+8]
0x18005034a  cmp     rdx, 0Fh
0x18005034e  jbe     short loc_18005038B
0x180050350  mov     rax, [rsp+1D8h+var_F0]
0x180050358  inc     rdx; struct std::nothrow_t *
0x18005035b  cmp     rdx, 1000h
0x180050362  jb      short loc_180050382
0x180050364  mov     rcx, [rax-8]
0x180050368  sub     rax, rcx
0x18005036b  sub     rax, 8
0x18005036f  cmp     rax, 1Fh
0x180050373  ja      short loc_18005037B
0x180050375  add     rdx, 27h ; '''
0x180050379  jmp     short loc_180050385
0x18005037b  mov     ecx, 5
0x180050380  int     29h; Win8: RtlFailFast(ecx)
0x180050382  mov     rcx, rax; void *
0x180050385  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005038a  nop
0x18005038b  jmp     loc_18005076B
0x180050390  lea     r8, [r14+28h]
0x180050394  mov     rdx, rsi; this
0x180050397  mov     rcx, r15; hRequest
0x18005039a  call    web__http__client__details__parse_winhttp_headers
0x18005039f  mov     rax, [r14+28h]
0x1800503a3  movzx   ecx, word ptr [rax+88h]
0x1800503aa  mov     eax, 191h
0x1800503af  cmp     cx, ax
0x1800503b2  jz      short loc_1800503BE
0x1800503b4  mov     eax, 197h
0x1800503b9  cmp     cx, ax
0x1800503bc  jnz     short loc_180050431
0x1800503be  xor     r8d, r8d
0x1800503c1  lea     rdx, [rsp+1D8h+var_168]
0x1800503c6  mov     rcx, r15
0x1800503c9  call    ?handle_authentication_failure@winhttp_client@details@client@http@web@@CA_NPEAXAEBV?$shared_ptr@Vwinhttp_request_context@details@client@http@web@@@std@@K@Z; web::http::client::details::winhttp_client::handle_authentication_failure(void *,std::shared_ptr<web::http::client::details::winhttp_request_context> const &,ulong)
0x1800503ce  test    al, al
0x1800503d0  jz      short loc_180050427
0x1800503d2  mov     rax, [rsp+1D8h+lpBuffer]
0x1800503d7  test    rax, rax
0x1800503da  jz      loc_180050E40
0x1800503e0  mov     rdx, qword ptr [rsp+1D8h+var_178]
0x1800503e5  sub     rdx, rax; struct std::nothrow_t *
0x1800503e8  cmp     rdx, 1000h
0x1800503ef  jb      short loc_18005040C
0x1800503f1  mov     rcx, [rax-8]
0x1800503f5  sub     rax, rcx
0x1800503f8  sub     rax, 8
0x1800503fc  cmp     rax, 1Fh
0x180050400  ja      loc_1800511DE
0x180050406  add     rdx, 27h ; '''
0x18005040a  jmp     short loc_18005040F
0x18005040c  mov     rcx, rax; void *
0x18005040f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180050414  xorps   xmm0, xmm0
0x180050417  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18005041d  mov     qword ptr [rsp+1D8h+var_178], r13
0x180050422  jmp     loc_180050E40
0x180050427  mov     rdi, [rsp+1D8h+var_168+8]
0x18005042c  mov     r14, [rsp+1D8h+var_168]
0x180050431  mov     rcx, r14; this
0x180050434  call    ?handle_compression@request_context@details@client@http@web@@QEAA_NXZ; web::http::client::details::request_context::handle_compression(void)
0x180050439  test    al, al
0x18005043b  jnz     short loc_180050442
0x18005043d  jmp     loc_18005076B
0x180050442  cmp     qword ptr [r14+60h], 0
0x180050447  jz      short loc_1800504B4
0x180050449  mov     rcx, [r14+8]; this
0x18005044d  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x180050452  cmp     byte ptr [rax+1B0h], 0
0x180050459  jnz     short loc_1800504B4
0x18005045b  mov     ecx, 10h; Size
0x180050460  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050465  mov     [rsp+1D8h+var_198], rax
0x18005046a  test    rax, rax
0x18005046d  jz      short loc_18005047F
0x18005046f  mov     [rax], r13
0x180050472  mov     dword ptr [rax+8], 1
0x180050479  mov     byte ptr [rax+0Ch], 0
0x18005047d  jmp     short loc_180050482
0x18005047f  mov     rax, r13
0x180050482  mov     [rsp+1D8h+var_198], rax
0x180050487  lea     rcx, [r14+140h]
0x18005048e  lea     rdx, [rsp+1D8h+var_198]
0x180050493  call    ??$?4U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@$0A@@?$unique_ptr@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper> &&)
0x180050498  mov     rcx, [rsp+1D8h+var_198]; void *
0x18005049d  test    rcx, rcx
0x1800504a0  jz      short loc_1800504AC
0x1800504a2  mov     edx, 10h; struct std::nothrow_t *
0x1800504a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800504ac  mov     byte ptr [r14+133h], 1
0x1800504b4  mov     rcx, r14; this
0x1800504b7  call    ?complete_headers@request_context@details@client@http@web@@QEAAXXZ; web::http::client::details::request_context::complete_headers(void)
0x1800504bc  mov     rcx, [r14+18h]
0x1800504c0  add     rcx, 90h
0x1800504c7  lea     rdx, ?HEAD@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::HEAD
0x1800504ce  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x1800504d3  mov     rcx, r14; this
0x1800504d6  test    al, al
0x1800504d8  jz      short loc_1800504F4
0x1800504da  xor     r8d, r8d; unsigned __int64
0x1800504dd  xor     edx, edx; unsigned __int8 *
0x1800504df  call    ?allocate_request_space@winhttp_request_context@details@client@http@web@@QEAAXPEAE_K@Z; web::http::client::details::winhttp_request_context::allocate_request_space(uchar *,unsigned __int64)
0x1800504e4  xor     edx, edx; unsigned __int64
0x1800504e6  mov     rcx, r14; this
0x1800504e9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800504ee  nop
0x1800504ef  jmp     loc_18005076B
0x1800504f4  mov     r8b, 1; bool
0x1800504f7  xor     edx, edx; unsigned int
0x1800504f9  call    ?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z; web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)
0x1800504fe  nop
0x1800504ff  jmp     loc_18005076B
0x180050504  mov     edx, [r9]
0x180050507  lea     rcx, [rsp+1D8h+Src]; Src
0x18005050f  call    _anonymous_namespace___generate_security_failure_message
0x180050514  mov     rcx, rax
0x180050517  xorps   xmm0, xmm0
0x18005051a  movups  [rsp+1D8h+var_A0], xmm0
0x180050522  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180050529  mov     [rsp+1D8h+var_A8], rax
0x180050531  mov     [rsp+1D8h+var_90], r13d
0x180050539  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180050540  mov     [rsp+1D8h+var_88], rax
0x180050548  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x180050550  mov     qword ptr [rsp+1D8h+var_70], r13
0x180050558  mov     qword ptr [rsp+1D8h+var_70+8], r13
0x180050560  movups  xmm0, xmmword ptr [rcx]
0x180050563  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x18005056b  mov     rax, [rcx+10h]
0x18005056f  mov     qword ptr [rsp+1D8h+var_70], rax
0x180050577  mov     rax, [rcx+18h]
0x18005057b  mov     qword ptr [rsp+1D8h+var_70+8], rax
0x180050583  mov     qword ptr [rcx+18h], 0Fh
0x18005058b  mov     byte ptr [rcx], 0
0x18005058e  mov     [rcx+10h], r13
0x180050592  mov     qword ptr [rcx+18h], 0Fh
0x18005059a  mov     byte ptr [rcx], 0
0x18005059d  lea     rdx, [rsp+1D8h+var_A8]
0x1800505a5  mov     rcx, r14
0x1800505a8  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800505ad  nop
0x1800505ae  lea     rcx, [rsp+1D8h+var_80]
0x1800505b6  call    ??1?$tuple@PEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::tuple<char const *,std::string>::~tuple<char const *,std::string>(void)
0x1800505bb  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800505c2  mov     [rsp+1D8h+var_A8], rax
0x1800505ca  lea     rcx, [rsp+1D8h+var_A0]
0x1800505d2  call    _o___std_exception_destroy_0
0x1800505d7  nop
0x1800505d8  test    rdi, rdi
0x1800505db  jz      loc_1800517A0
0x1800505e1  mov     esi, 0FFFFFFFFh
0x1800505e6  jmp     loc_18005176D
0x1800505eb  mov     rax, [r14+80h]
0x1800505f2  test    rax, rax
0x1800505f5  jz      short loc_180050614
0x1800505f7  dec     rax
0x1800505fa  mov     [r14+80h], rax
0x180050601  test    rdi, rdi
0x180050604  jz      loc_1800517A0
0x18005060a  mov     esi, 0FFFFFFFFh
0x18005060f  jmp     loc_18005176D
0x180050614  mov     [rsp+1D8h+dwBufferLength], r13d
0x180050619  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x18005061e  lea     rax, [rsp+1D8h+dwBufferLength]
0x180050623  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180050628  xor     r9d, r9d; lpBuffer
0x18005062b  xor     r8d, r8d; pwszName
0x18005062e  mov     edx, 16h; dwInfoLevel
0x180050633  mov     rcx, r15; hRequest
0x180050636  call    cs:__imp_WinHttpQueryHeaders
0x18005063c  xorps   xmm0, xmm0
  ... truncated ...
```
