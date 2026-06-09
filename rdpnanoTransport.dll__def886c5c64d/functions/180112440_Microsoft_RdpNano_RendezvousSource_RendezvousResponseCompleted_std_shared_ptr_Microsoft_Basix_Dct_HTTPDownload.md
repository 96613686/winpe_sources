# Microsoft::RdpNano::RendezvousSource::RendezvousResponseCompleted(std::shared_ptr<Microsoft::Basix::Dct::HTTPDownload>,std::exception_ptr)

- ea: `0x180112440`
- end: `0x180113258`
- name: `?RendezvousResponseCompleted@RendezvousSource@RdpNano@Microsoft@@AEAAXV?$shared_ptr@VHTTPDownload@Dct@Basix@Microsoft@@@std@@Vexception_ptr@5@@Z`
- size: `3608`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x18001902c`
- `0x18001d1e0`
- `0x180024700`
- `0x180027b84`
- `0x180027bf8`
- `0x18002a8ec`
- `0x18003d8fc`
- `0x1800f64ec`
- `0x1800f7968`
- `0x1800f8ca0`
- `0x1800f9030`
- `0x1800f97c0`
- `0x1800f9864`
- `0x180106038`
- `0x1801061d0`
- `0x180107b8c`
- `0x1801093f4`
- `0x18010c374`
- `0x18010e434`
- `0x180112440`
- `0x1801ad7b4`
- `0x18028ab9c`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x1802ebbac`
- `0x1802f6ab4`
- `0x1802f73dc`
- `0x180311e54`
- `0x180312e30`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180330b40`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x180113123`: `Failed in RendezvousResponseCompleted!`
- `0x18011320a`: `Got completion for unexpected fetch operation`
- `0x180112954`: `clientHeartBeatReply.uri`
- `0x180112bf5`: `RendezvousResponseCompleted: gatewayLoadBalancerMethod=%s, diagRing=%s, diagRegion=%s, diagActiveColor=%s, heartBeatUri=%s, heartBeatReportInTimeMs=%lld`
- `0x180112e8e`: `RendezvousResponseCompleted in RendezvousChannel. Establishing link, requestId=%s,connectionId=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=78 #try_helpers=1
void __fastcall Microsoft::RdpNano::RendezvousSource::RendezvousResponseCompleted(
        Microsoft::RdpNano::RendezvousSource *a1,
        _QWORD *a2,
        void *a3)
{
  _QWORD *v4; // r12
  volatile signed __int32 *v6; // rsi
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int128 *v11; // rax
  __int128 *v12; // rax
  __int128 *v13; // rax
  __int128 *v14; // rax
  __int128 *v15; // rax
  __int128 *v16; // rax
  __int64 v17; // r8
  _QWORD *v18; // rsi
  unsigned __int64 v19; // rcx
  char *v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  const char *v23; // rdx
  const char *v24; // r9
  __int128 *v25; // rsi
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  volatile signed __int32 *v30; // rsi
  __int64 ResponseHeaders; // rsi
  __int128 *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // r12
  const char *v35; // r9
  _QWORD *v36; // rsi
  volatile signed __int32 *v37; // rsi
  volatile signed __int32 *v38; // rsi
  __int64 v39; // rax
  Microsoft::Basix *v40; // rcx
  const struct std::error_category *v41; // rax
  int v42; // ebx
  __int64 v43; // rax
  char v44; // bl
  Microsoft::RdpNano::RendezvousSource *v45; // rdi
  __int64 v46; // rdx
  signed __int32 v47; // eax
  signed __int32 v48; // ett
  __int128 v49; // rcx
  __int64 v50; // rax
  const char *v51; // [rsp+20h] [rbp-688h]
  const char *v52; // [rsp+28h] [rbp-680h]
  const char *v53; // [rsp+30h] [rbp-678h]
  __int64 v54; // [rsp+38h] [rbp-670h]
  __int128 v55; // [rsp+58h] [rbp-650h] BYREF
  int v56[2]; // [rsp+68h] [rbp-640h] BYREF
  __int128 v57; // [rsp+70h] [rbp-638h] BYREF
  __int128 v58; // [rsp+80h] [rbp-628h]
  char v59; // [rsp+90h] [rbp-618h]
  __int128 *v60; // [rsp+98h] [rbp-610h]
  __int128 v61; // [rsp+A0h] [rbp-608h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-5F8h]
  char v63; // [rsp+C0h] [rbp-5E8h]
  __int128 *v64; // [rsp+C8h] [rbp-5E0h]
  _QWORD *v65; // [rsp+D0h] [rbp-5D8h]
  Microsoft::RdpNano::RendezvousSource *v66; // [rsp+D8h] [rbp-5D0h]
  _QWORD *v67; // [rsp+E0h] [rbp-5C8h]
  _OWORD v68[2]; // [rsp+E8h] [rbp-5C0h] BYREF
  _OWORD v69[2]; // [rsp+108h] [rbp-5A0h] BYREF
  __int64 v70; // [rsp+128h] [rbp-580h] BYREF
  _QWORD *v71; // [rsp+130h] [rbp-578h]
  _QWORD *v72; // [rsp+138h] [rbp-570h]
  __int128 v73; // [rsp+140h] [rbp-568h] BYREF
  __int128 v74; // [rsp+150h] [rbp-558h]
  char v75; // [rsp+160h] [rbp-548h]
  __int128 *v76; // [rsp+168h] [rbp-540h]
  _OWORD v77[2]; // [rsp+1D0h] [rbp-4D8h] BYREF
  Microsoft::Basix::SystemException *v78; // [rsp+1F0h] [rbp-4B8h] BYREF
  const std::exception *v79; // [rsp+1F8h] [rbp-4B0h] BYREF
  _BYTE v80[128]; // [rsp+210h] [rbp-498h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+290h] [rbp-418h] BYREF
  void *v82; // [rsp+320h] [rbp-388h]
  char v83[8]; // [rsp+328h] [rbp-380h] BYREF
  __int128 v84; // [rsp+330h] [rbp-378h] BYREF
  __int128 v85; // [rsp+340h] [rbp-368h]
  _OWORD v86[2]; // [rsp+350h] [rbp-358h] BYREF
  __int128 v87; // [rsp+370h] [rbp-338h] BYREF
  __int128 v88; // [rsp+380h] [rbp-328h]
  _OWORD v89[2]; // [rsp+390h] [rbp-318h] BYREF
  __int64 v90; // [rsp+3B0h] [rbp-2F8h]
  _QWORD v91[2]; // [rsp+3B8h] [rbp-2F0h] BYREF
  unsigned __int64 v92; // [rsp+3C8h] [rbp-2E0h]
  unsigned __int64 v93; // [rsp+3D0h] [rbp-2D8h]
  _QWORD v94[4]; // [rsp+3D8h] [rbp-2D0h] BYREF
  char v95[8]; // [rsp+3F8h] [rbp-2B0h] BYREF
  _BYTE v96[32]; // [rsp+400h] [rbp-2A8h] BYREF
  _QWORD v97[4]; // [rsp+420h] [rbp-288h] BYREF
  _QWORD v98[4]; // [rsp+440h] [rbp-268h] BYREF
  _QWORD v99[3]; // [rsp+460h] [rbp-248h] BYREF
  unsigned __int64 v100; // [rsp+478h] [rbp-230h]
  _QWORD v101[30]; // [rsp+480h] [rbp-228h] BYREF
  _QWORD v102[30]; // [rsp+570h] [rbp-138h] BYREF

  v4 = a2;
  *(_QWORD *)&v55 = a2;
  v66 = a1;
  v65 = a2;
  v82 = a3;
  if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                           a3,
                           a2) )
  {
    if ( !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                             v4,
                             (char *)a1 + 160) )
    {
      std::string::string(v68, "C:\\__w\\1\\s\\rdnanolib\\rdnano\\rendezvouschannelsource.cpp");
      std::string::string(v69, "Got completion for unexpected fetch operation");
      Microsoft::Basix::Exception::Exception(v80, v69, v68, 519);
      throw (Microsoft::Basix::Exception *)v80;
    }
    v90 = 0;
    v89[0] = 0;
    v89[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v89[0]) = 0;
    v8 = operator new(0x20u);
    v67 = v8;
    if ( v8 )
      v9 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v8);
    else
      v9 = 0;
    v90 = v9;
    memset(v102, 0, sizeof(v102));
    v10 = Microsoft::Basix::Containers::FlexIBuffer::ToString((char *)a1 + 176, v68);
    std::istringstream::istringstream(v102, v10, 1);
    std::string::_Tidy_deallocate(v68);
    memset(v101, 0, 0x78u);
    std::istream::istream(v101, &v102[2], 0, 1);
    boost::property_tree::json_parser::read_json<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(
      v101,
      v89);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, (const char *)&Str1, 0);
    v57 = 0;
    v58 = 0;
    std::string::_Construct<1,char const *>(&v57, "gatewayLoadBalancerMethod", 25);
    v59 = 46;
    v11 = &v57;
    if ( *((_QWORD *)&v58 + 1) > 0xFu )
      v11 = (__int128 *)v57;
    v60 = v11;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v89,
      v94,
      &v57,
      &v84);
    std::string::_Tidy_deallocate(&v57);
    std::string::_Tidy_deallocate(&v84);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, (const char *)&Str1, 0);
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&v61, "gatewayDiagnosticsInfo.ring", 27);
    v63 = 46;
    v12 = &v61;
    if ( *((_QWORD *)&v62 + 1) > 0xFu )
      v12 = (__int128 *)v61;
    v64 = v12;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v89,
      v98,
      &v61,
      &v84);
    std::string::_Tidy_deallocate(&v61);
    std::string::_Tidy_deallocate(&v84);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, (const char *)&Str1, 0);
    v57 = 0;
    v58 = 0;
    std::string::_Construct<1,char const *>(&v57, "gatewayDiagnosticsInfo.region", 29);
    v59 = 46;
    v13 = &v57;
    if ( *((_QWORD *)&v58 + 1) > 0xFu )
      v13 = (__int128 *)v57;
    v60 = v13;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v89,
      v97,
      &v57,
      &v84);
    std::string::_Tidy_deallocate(&v57);
    std::string::_Tidy_deallocate(&v84);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, (const char *)&Str1, 0);
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&v61, "gatewayDiagnosticsInfo.activeColor", 34);
    v63 = 46;
    v14 = &v61;
    if ( *((_QWORD *)&v62 + 1) > 0xFu )
      v14 = (__int128 *)v61;
    v64 = v14;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v89,
      v99,
      &v61,
      &v84);
    std::string::_Tidy_deallocate(&v61);
    std::string::_Tidy_deallocate(&v84);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, (const char *)&Str1, 0);
    v57 = 0;
    v58 = 0;
    std::string::_Construct<1,char const *>(&v57, "clientHeartBeatReply.uri", 24);
    v59 = 46;
    v15 = &v57;
    if ( *((_QWORD *)&v58 + 1) > 0xFu )
      v15 = (__int128 *)v57;
    v60 = v15;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v89,
      v91,
      &v57,
      &v84);
    std::string::_Tidy_deallocate(&v57);
    std::string::_Tidy_deallocate(&v84);
    *(_QWORD *)v56 = 0;
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&v61, "clientHeartBeatReply.reportInTime", 33);
    v63 = 46;
    v16 = &v61;
    if ( *((_QWORD *)&v62 + 1) > 0xFu )
      v16 = (__int128 *)v61;
    v64 = v16;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::chrono::duration<__int64,std::ratio<1,1000>>>(
      v89,
      &v70,
      &v61,
      v56);
    std::string::_Tidy_deallocate(&v61);
    v18 = v91;
    if ( v93 > 0xF )
      v18 = (_QWORD *)v91[0];
    v19 = v92;
    if ( !v92
      || (_mm_lfence(),
          v20 = (char *)v18 + v92,
          LOBYTE(v17) = 63,
          v21 = std::_Find_vectorized<char const,char>(v18, (char *)v18 + v92, v17),
          v19 = v92,
          (char *)v21 == v20) )
    {
      v22 = -1;
    }
    else
    {
      v22 = v21 - (_QWORD)v18;
    }
    v87 = 0;
    v88 = 0;
    if ( v19 < v22 )
      v22 = v19;
    v23 = (const char *)v91;
    if ( v93 > 0xF )
      v23 = (const char *)v91[0];
    std::string::_Construct<1,char const *>(&v87, v23, v22);
    v86[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v86);
    if ( *(_QWORD *)&v86[0] && *(_BYTE *)(*(_QWORD *)&v86[0] + 128LL) )
    {
      v25 = &v87;
      if ( *((_QWORD *)&v88 + 1) > 0xFu )
        v25 = (__int128 *)v87;
      v26 = v99;
      if ( v100 > 0xF )
        v26 = (_QWORD *)v99[0];
      *(_QWORD *)v56 = v26;
      v27 = v97;
      if ( v97[3] > 0xFu )
        v27 = (_QWORD *)v97[0];
      v71 = v27;
      v28 = v98;
      if ( v98[3] > 0xFu )
        v28 = (_QWORD *)v98[0];
      v72 = v28;
      v29 = v94;
      if ( v94[3] > 0xFu )
        v29 = (_QWORD *)v94[0];
      v67 = v29;
      v84 = 0;
      v85 = 0;
      std::string::_Construct<1,char const *>(
        &v84,
        "RendezvousResponseCompleted: gatewayLoadBalancerMethod=%s, diagRing=%s, diagRegion=%s, diagActiveColor=%s, heart"
        "BeatUri=%s, heartBeatReportInTimeMs=%lld",
        (const char *)0x98,
        v24,
        v51,
        v52,
        v53,
        v54);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,char const *,char const *,char const *,__int64>(
        (unsigned int)v86,
        (unsigned int)"RENDEZVOUS",
        (unsigned int)&v84,
        (_DWORD)v67,
        (__int64)v72,
        (__int64)v71,
        *(__int64 *)v56,
        (__int64)v25,
        v70);
      std::string::_Tidy_deallocate(&v84);
    }
    v30 = (volatile signed __int32 *)*((_QWORD *)&v86[0] + 1);
    if ( *((_QWORD *)&v86[0] + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v86[0] + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
        if ( !_InterlockedDecrement(v30 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
    ResponseHeaders = Microsoft::Basix::Dct::HTTPDownload::GetResponseHeaders(*v4, &v57);
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, "x-ms-request-id", 15);
    Microsoft::Basix::HTTP::Headers::GetOptional(ResponseHeaders, v95, &v84);
    std::string::_Tidy_deallocate(&v84);
    Microsoft::Basix::HTTP::Headers::~Headers((Microsoft::Basix::HTTP::Headers *)&v57);
    v86[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v86);
    if ( *(_QWORD *)&v86[0] && *(_BYTE *)(*(_QWORD *)&v86[0] + 128LL) )
    {
      memset(v68, 0, sizeof(v68));
      std::string::_Construct<1,char const *>(v68, (const char *)&Str1, 0);
      v73 = 0;
      v74 = 0;
      std::string::_Construct<1,char const *>(&v73, "connectionId", 12);
      v75 = 46;
      v32 = &v73;
      if ( *((_QWORD *)&v74 + 1) > 0xFu )
        v32 = (__int128 *)v73;
      v76 = v32;
      v33 = (__int64 *)boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
                         v89,
                         &v61,
                         &v73,
                         v68);
      v34 = (__int64)v33;
      if ( (unsigned __int64)v33[3] > 0xF )
        v34 = *v33;
      memset(v77, 0, sizeof(v77));
      std::string::_Construct<1,char const *>(v77, (const char *)&Str1, 0);
      if ( v95[0] )
        v36 = (_QWORD *)(*(__int64 (__fastcall **)(_BYTE *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v96);
      else
        v36 = v77;
      if ( v36[3] > 0xFu )
        v36 = (_QWORD *)*v36;
      memset(v69, 0, sizeof(v69));
      std::string::_Construct<1,char const *>(
        v69,
        "RendezvousResponseCompleted in RendezvousChannel. Establishing link, requestId=%s,connectionId=%s",
        (const char *)0x61,
        v35);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
        (unsigned int)v86,
        (unsigned int)"RENDEZVOUS",
        (unsigned int)v69,
        (_DWORD)v36,
        v34);
      std::string::_Tidy_deallocate(v69);
      std::string::_Tidy_deallocate(v77);
      std::string::_Tidy_deallocate(&v61);
      std::string::_Tidy_deallocate(&v73);
      std::string::_Tidy_deallocate(v68);
      v4 = (_QWORD *)v55;
    }
    v37 = (volatile signed __int32 *)*((_QWORD *)&v86[0] + 1);
    if ( *((_QWORD *)&v86[0] + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v86[0] + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( !_InterlockedDecrement(v37 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::operator=((char *)a1 + 392, v89);
    *((_BYTE *)a1 + 432) = 1;
    Microsoft::RdpNano::RendezvousSource::CreateWebsocketFromRendezvousResponse(a1);
    if ( !Microsoft::Basix::Dct::detail::BasicStateManagement::IsOpened(a1) )
    {
      (*(void (__fastcall **)(Microsoft::RdpNano::RendezvousSource *, _QWORD, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, 0, 0);
      (*(void (__fastcall **)(Microsoft::RdpNano::RendezvousSource *, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0, 0);
    }
    if ( v95[0] )
    {
      std::string::_Tidy_deallocate(v96);
      v95[0] = 0;
    }
    std::string::_Tidy_deallocate(&v87);
    std::string::_Tidy_deallocate(v91);
    std::string::_Tidy_deallocate(v99);
    std::string::_Tidy_deallocate(v97);
    std::string::_Tidy_deallocate(v98);
    std::string::_Tidy_deallocate(v94);
    *(_QWORD *)((char *)v101 + *(int *)(v101[0] + 4LL)) = &std::istream::`vftable';
    *(_DWORD *)((char *)&v100 + *(int *)(v101[0] + 4LL) + 4) = *(_DWORD *)(v101[0] + 4LL) - 24;
    v101[3] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v101[3]);
    std::istringstream::~istringstream(&v102[18]);
    v102[18] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v102[18]);
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::~basic_ptree<std::string,std::string,std::less<std::string>>(v89);
    v38 = (volatile signed __int32 *)v4[1];
    if ( v38 && _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
    __ExceptionPtrDestroy(a3);
    return;
  }
  std::string::string(&v84, "Failed in RendezvousResponseCompleted!");
  v56[0] = -1950613505;
  v39 = std::exception_ptr::exception_ptr((std::exception_ptr *)v86, (const struct std::exception_ptr *)a3);
  try
  {
    std::rethrow_exception(v39);
  }
  catch ( Microsoft::Basix::SystemException *v78 )
  {
    v56[0] = *((_DWORD *)v78 + 6);
    v42 = v56[0];
    v43 = (*(__int64 (__fastcall **)(Microsoft::Basix::SystemException *))(*(_QWORD *)v78 + 8LL))(v78);
    std::string::assign(&v84, v43);
    if ( v42 != -2145844847 )
      goto LABEL_77;
    v83[0] = 0;
    v44 = ((__int64 (__fastcall *)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data2)(v83);
    v45 = v66;
    *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v66 + 288) = v44;
    *((_BYTE *)v45 + 561) = 1;
    v55 = 0;
    if ( *((_QWORD *)v45 + 48) )
    {
      v46 = *((_QWORD *)v45 + 48);
      v47 = *(_DWORD *)(v46 + 8);
      while ( v47 )
      {
        v48 = v47;
        v47 = _InterlockedCompareExchange((volatile signed __int32 *)(v46 + 8), v47 + 1, v47);
        if ( v48 == v47 )
        {
          *(_QWORD *)&v49 = *((_QWORD *)v45 + 47);
          *(_QWORD *)&v55 = v49;
          *((_QWORD *)&v49 + 1) = *((_QWORD *)v45 + 48);
          *((_QWORD *)&v55 + 1) = *((_QWORD *)&v49 + 1);
          goto LABEL_87;
        }
      }
    }
    v49 = v55;
LABEL_87:
    if ( (_QWORD)v49 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49 + 8LL))(v49);
    if ( *((_QWORD *)&v49 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v49 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v49 + 1))(*((_QWORD *)&v49 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v49 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v49 + 1) + 8LL))(*((_QWORD *)&v49 + 1));
      }
    }
    std::string::_Tidy_deallocate(&v84);
    v6 = (volatile signed __int32 *)v65[1];
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    __ExceptionPtrDestroy(v82);
    return;
  }
  catch ( const std::exception *v79 )
  {
    v50 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v79 + 8LL))(v79);
    std::string::operator=(&v84, v50);
  }
LABEL_77:
  std::string::string(v68, (const char *)&Str1);
  std::string::string(v69, "C:\\__w\\1\\s\\rdnanolib\\rdnano\\rendezvouschannelsource.cpp");
  v41 = Microsoft::Basix::WindowsCategory(v40);
  v86[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v55, v56[0], v41);
  Microsoft::Basix::SystemException::SystemException(
    (unsigned int)pExceptionObject,
    (unsigned int)v86,
    (unsigned int)&v84,
    (unsigned int)v69,
    516,
    (__int64)v68);
  throw (Microsoft::Basix::SystemException *)pExceptionObject;
}

```

## disassembly

```asm
0x180112440  push    rbx
0x180112442  push    rsi
0x180112443  push    rdi
0x180112444  push    r12
0x180112446  push    r13
0x180112448  push    r14
0x18011244a  push    r15
0x18011244c  mov     eax, 670h
0x180112451  call    _alloca_probe
0x180112456  sub     rsp, rax
0x180112459  mov     rax, cs:__security_cookie
0x180112460  xor     rax, rsp
0x180112463  mov     [rsp+6A8h+var_48], rax
0x18011246b  mov     r13, r8
0x18011246e  mov     r12, rdx
0x180112471  mov     qword ptr [rsp+6A8h+var_650], rdx
0x180112476  mov     r14, rcx
0x180112479  mov     [rsp+6A8h+var_5D0], rcx
0x180112481  mov     [rsp+6A8h+var_5D8], rdx
0x180112489  mov     [rsp+6A8h+var_388], r8
0x180112491  xor     edi, edi
0x180112493  mov     [rsp+6A8h+var_658], edi
0x180112497  mov     rcx, r8
0x18011249a  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x18011249f  test    al, al
0x1801124a1  jnz     loc_180113123
0x1801124a7  jmp     short loc_180112514
0x1801124a9  lea     rcx, [rsp+6A8h+var_378]
0x1801124b1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801124b6  nop
0x1801124b7  mov     rax, [rsp+6A8h+var_5D8]
0x1801124bf  mov     rsi, [rax+8]
0x1801124c3  test    rsi, rsi
0x1801124c6  jz      short loc_180112502
0x1801124c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801124cc  mov     eax, ebx
0x1801124ce  lock xadd [rsi+8], eax
0x1801124d3  add     eax, ebx
0x1801124d5  jnz     short loc_180112502
0x1801124d7  mov     rax, [rsi]
0x1801124da  mov     rcx, rsi
0x1801124dd  mov     rax, [rax]
0x1801124e0  call    cs:__guard_dispatch_icall_fptr
0x1801124e6  mov     eax, ebx
0x1801124e8  lock xadd [rsi+0Ch], eax
0x1801124ed  add     eax, ebx
0x1801124ef  jnz     short loc_180112502
0x1801124f1  mov     rax, [rsi]
0x1801124f4  mov     rcx, rsi
0x1801124f7  mov     rax, [rax+8]
0x1801124fb  call    cs:__guard_dispatch_icall_fptr
0x180112501  nop
0x180112502  mov     rcx, [rsp+6A8h+var_388]; void *
0x18011250a  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18011250f  jmp     loc_180113100
0x180112514  lea     rdx, [r14+0A0h]
0x18011251b  mov     rcx, r12
0x18011251e  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x180112523  test    al, al
0x180112525  jz      loc_1801131F5
0x18011252b  xorps   xmm0, xmm0
0x18011252e  mov     [rsp+6A8h+var_2F8], rdi
0x180112536  movups  [rsp+6A8h+var_318], xmm0
0x18011253e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180112546  movdqu  [rsp+6A8h+var_308], xmm1
0x18011254f  mov     byte ptr [rsp+6A8h+var_318], dil
0x180112557  mov     ecx, 20h ; ' '; Size
0x18011255c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180112561  mov     [rsp+6A8h+var_5C8], rax
0x180112569  test    rax, rax
0x18011256c  jz      short loc_180112578
0x18011256e  mov     rcx, rax
0x180112571  call    ??0?$multi_index_container@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@U?$indexed_by@U?$sequenced@U?$tag@Una@mpl@boost@@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@@multi_index@boost@@@multi_index@boost@@U?$ordered_non_unique@U?$tag@Uby_name@subs@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@Una@mpl@5@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@@multi_index@boost@@U?$member@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@$0A@@23@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@23@Una@mpl@3@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@@multi_index@boost@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@multi_index@boost@@QEAA@XZ
0x180112576  jmp     short loc_18011257B
0x180112578  mov     rax, rdi
0x18011257b  mov     [rsp+6A8h+var_2F8], rax
0x180112583  xor     edx, edx; Val
0x180112585  mov     r8d, 0F0h; Size
0x18011258b  lea     rcx, [rsp+6A8h+var_138]; void *
0x180112593  call    memset
0x180112598  lea     rcx, [r14+0B0h]
0x18011259f  lea     rdx, [rsp+6A8h+var_5C0]
0x1801125a7  call    ?ToString@FlexIBuffer@Containers@Basix@Microsoft@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Basix::Containers::FlexIBuffer::ToString(void)
0x1801125ac  nop
0x1801125ad  mov     ebx, 1
0x1801125b2  mov     r9d, ebx
0x1801125b5  mov     r8d, ebx
0x1801125b8  mov     rdx, rax
0x1801125bb  lea     rcx, [rsp+6A8h+var_138]
0x1801125c3  call    ??0?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::istringstream::istringstream(std::string const &,int)
0x1801125c8  nop
0x1801125c9  lea     rcx, [rsp+6A8h+var_5C0]
0x1801125d1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801125d6  xor     edx, edx; Val
0x1801125d8  lea     r8d, [rbx+77h]; Size
0x1801125dc  lea     rcx, [rsp+6A8h+var_228]; void *
0x1801125e4  call    memset
0x1801125e9  mov     r9d, ebx
0x1801125ec  xor     r8d, r8d
0x1801125ef  lea     rdx, [rsp+6A8h+var_128]
0x1801125f7  lea     rcx, [rsp+6A8h+var_228]
0x1801125ff  call    ??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x180112604  nop
0x180112605  lea     rdx, [rsp+6A8h+var_318]
0x18011260d  lea     rcx, [rsp+6A8h+var_228]
0x180112615  call    ??$read_json@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YAXAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@AEAV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@12@@Z; boost::property_tree::json_parser::read_json<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(std::istream &,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>> &)
0x18011261a  xorps   xmm0, xmm0
0x18011261d  movups  [rsp+6A8h+var_378], xmm0
0x180112625  xorps   xmm1, xmm1
0x180112628  movdqu  [rsp+6A8h+var_368], xmm1
0x180112631  xor     r8d, r8d
0x180112634  lea     r15, Str1
0x18011263b  mov     rdx, r15
0x18011263e  lea     rcx, [rsp+6A8h+var_378]
0x180112646  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011264b  nop
0x18011264c  xorps   xmm0, xmm0
0x18011264f  movups  [rsp+6A8h+var_638], xmm0
0x180112654  xorps   xmm1, xmm1
0x180112657  movdqu  [rsp+6A8h+var_628], xmm1
0x180112660  lea     r8d, [rbx+18h]
0x180112664  lea     rdx, aGatewayloadbal; "gatewayLoadBalancerMethod"
0x18011266b  lea     rcx, [rsp+6A8h+var_638]
0x180112670  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180112675  mov     [rsp+6A8h+var_618], 2Eh ; '.'
0x18011267d  lea     rax, [rsp+6A8h+var_638]
0x180112682  cmp     qword ptr [rsp+6A8h+var_628+8], 0Fh
0x18011268b  cmova   rax, qword ptr [rsp+6A8h+var_638]
0x180112691  mov     [rsp+6A8h+var_610], rax
0x180112699  lea     r9, [rsp+6A8h+var_378]
0x1801126a1  lea     r8, [rsp+6A8h+var_638]
0x1801126a6  lea     rdx, [rsp+6A8h+var_2D0]
0x1801126ae  lea     rcx, [rsp+6A8h+var_318]
0x1801126b6  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x1801126bb  nop
0x1801126bc  lea     rcx, [rsp+6A8h+var_638]
0x1801126c1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801126c6  nop
0x1801126c7  lea     rcx, [rsp+6A8h+var_378]
0x1801126cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801126d4  xorps   xmm0, xmm0
0x1801126d7  movups  [rsp+6A8h+var_378], xmm0
0x1801126df  xorps   xmm1, xmm1
0x1801126e2  movdqu  [rsp+6A8h+var_368], xmm1
0x1801126eb  xor     r8d, r8d
0x1801126ee  mov     rdx, r15
0x1801126f1  lea     rcx, [rsp+6A8h+var_378]
0x1801126f9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801126fe  nop
0x1801126ff  xorps   xmm0, xmm0
0x180112702  movups  [rsp+6A8h+var_608], xmm0
0x18011270a  xorps   xmm1, xmm1
0x18011270d  movdqu  [rsp+6A8h+var_5F8], xmm1
0x180112716  lea     r8d, [rbx+1Ah]
0x18011271a  lea     rdx, aGatewaydiagnos_1; "gatewayDiagnosticsInfo.ring"
0x180112721  lea     rcx, [rsp+6A8h+var_608]
0x180112729  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011272e  mov     [rsp+6A8h+var_5E8], 2Eh ; '.'
0x180112736  lea     rax, [rsp+6A8h+var_608]
0x18011273e  cmp     qword ptr [rsp+6A8h+var_5F8+8], 0Fh
0x180112747  cmova   rax, qword ptr [rsp+6A8h+var_608]
0x180112750  mov     [rsp+6A8h+var_5E0], rax
0x180112758  lea     r9, [rsp+6A8h+var_378]
0x180112760  lea     r8, [rsp+6A8h+var_608]
0x180112768  lea     rdx, [rsp+6A8h+var_268]
0x180112770  lea     rcx, [rsp+6A8h+var_318]
0x180112778  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x18011277d  nop
0x18011277e  lea     rcx, [rsp+6A8h+var_608]
0x180112786  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011278b  nop
0x18011278c  lea     rcx, [rsp+6A8h+var_378]
0x180112794  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180112799  xorps   xmm0, xmm0
0x18011279c  movups  [rsp+6A8h+var_378], xmm0
0x1801127a4  xorps   xmm1, xmm1
0x1801127a7  movdqu  [rsp+6A8h+var_368], xmm1
0x1801127b0  xor     r8d, r8d
0x1801127b3  mov     rdx, r15
0x1801127b6  lea     rcx, [rsp+6A8h+var_378]
0x1801127be  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801127c3  nop
0x1801127c4  xorps   xmm0, xmm0
0x1801127c7  movups  [rsp+6A8h+var_638], xmm0
0x1801127cc  xorps   xmm1, xmm1
0x1801127cf  movdqu  [rsp+6A8h+var_628], xmm1
0x1801127d8  lea     r8d, [rbx+1Ch]
0x1801127dc  lea     rdx, aGatewaydiagnos_2; "gatewayDiagnosticsInfo.region"
0x1801127e3  lea     rcx, [rsp+6A8h+var_638]
0x1801127e8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801127ed  mov     [rsp+6A8h+var_618], 2Eh ; '.'
0x1801127f5  lea     rax, [rsp+6A8h+var_638]
0x1801127fa  cmp     qword ptr [rsp+6A8h+var_628+8], 0Fh
0x180112803  cmova   rax, qword ptr [rsp+6A8h+var_638]
0x180112809  mov     [rsp+6A8h+var_610], rax
0x180112811  lea     r9, [rsp+6A8h+var_378]
0x180112819  lea     r8, [rsp+6A8h+var_638]
0x18011281e  lea     rdx, [rsp+6A8h+var_288]
0x180112826  lea     rcx, [rsp+6A8h+var_318]
0x18011282e  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x180112833  nop
0x180112834  lea     rcx, [rsp+6A8h+var_638]
0x180112839  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011283e  nop
0x18011283f  lea     rcx, [rsp+6A8h+var_378]
0x180112847  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011284c  xorps   xmm0, xmm0
0x18011284f  movups  [rsp+6A8h+var_378], xmm0
0x180112857  xorps   xmm1, xmm1
0x18011285a  movdqu  [rsp+6A8h+var_368], xmm1
0x180112863  xor     r8d, r8d
0x180112866  mov     rdx, r15
0x180112869  lea     rcx, [rsp+6A8h+var_378]
0x180112871  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180112876  nop
0x180112877  xorps   xmm0, xmm0
0x18011287a  movups  [rsp+6A8h+var_608], xmm0
0x180112882  xorps   xmm1, xmm1
0x180112885  movdqu  [rsp+6A8h+var_5F8], xmm1
0x18011288e  lea     r8d, [rbx+21h]
0x180112892  lea     rdx, aGatewaydiagnos_0; "gatewayDiagnosticsInfo.activeColor"
0x180112899  lea     rcx, [rsp+6A8h+var_608]
0x1801128a1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801128a6  mov     [rsp+6A8h+var_5E8], 2Eh ; '.'
0x1801128ae  lea     rax, [rsp+6A8h+var_608]
0x1801128b6  cmp     qword ptr [rsp+6A8h+var_5F8+8], 0Fh
0x1801128bf  cmova   rax, qword ptr [rsp+6A8h+var_608]
0x1801128c8  mov     [rsp+6A8h+var_5E0], rax
0x1801128d0  lea     r9, [rsp+6A8h+var_378]
0x1801128d8  lea     r8, [rsp+6A8h+var_608]
0x1801128e0  lea     rdx, [rsp+6A8h+var_248]
0x1801128e8  lea     rcx, [rsp+6A8h+var_318]
0x1801128f0  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x1801128f5  nop
0x1801128f6  lea     rcx, [rsp+6A8h+var_608]
0x1801128fe  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180112903  nop
0x180112904  lea     rcx, [rsp+6A8h+var_378]
0x18011290c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180112911  xorps   xmm0, xmm0
0x180112914  movups  [rsp+6A8h+var_378], xmm0
0x18011291c  xorps   xmm1, xmm1
0x18011291f  movdqu  [rsp+6A8h+var_368], xmm1
0x180112928  xor     r8d, r8d
0x18011292b  mov     rdx, r15
0x18011292e  lea     rcx, [rsp+6A8h+var_378]
0x180112936  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011293b  nop
0x18011293c  xorps   xmm0, xmm0
0x18011293f  movups  [rsp+6A8h+var_638], xmm0
0x180112944  xorps   xmm1, xmm1
0x180112947  movdqu  [rsp+6A8h+var_628], xmm1
0x180112950  lea     r8d, [rbx+17h]
0x180112954  lea     rdx, aClientheartbea_18; "clientHeartBeatReply.uri"
0x18011295b  lea     rcx, [rsp+6A8h+var_638]
0x180112960  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180112965  mov     [rsp+6A8h+var_618], 2Eh ; '.'
0x18011296d  lea     rax, [rsp+6A8h+var_638]
0x180112972  cmp     qword ptr [rsp+6A8h+var_628+8], 0Fh
0x18011297b  cmova   rax, qword ptr [rsp+6A8h+var_638]
0x180112981  mov     [rsp+6A8h+var_610], rax
0x180112989  lea     r9, [rsp+6A8h+var_378]
0x180112991  lea     r8, [rsp+6A8h+var_638]
0x180112996  lea     rdx, [rsp+6A8h+var_2F0]
0x18011299e  lea     rcx, [rsp+6A8h+var_318]
0x1801129a6  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x1801129ab  nop
0x1801129ac  lea     rcx, [rsp+6A8h+var_638]
0x1801129b1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801129b6  nop
0x1801129b7  lea     rcx, [rsp+6A8h+var_378]
0x1801129bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801129c4  mov     qword ptr [rsp+6A8h+var_640], rdi
0x1801129c9  xorps   xmm0, xmm0
0x1801129cc  movups  [rsp+6A8h+var_608], xmm0
0x1801129d4  xorps   xmm1, xmm1
0x1801129d7  movdqu  [rsp+6A8h+var_5F8], xmm1
0x1801129e0  lea     r8d, [rbx+20h]
0x1801129e4  lea     rdx, aClientheartbea_20; "clientHeartBeatReply.reportInTime"
0x1801129eb  lea     rcx, [rsp+6A8h+var_608]
0x1801129f3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801129f8  mov     [rsp+6A8h+var_5E8], 2Eh ; '.'
0x180112a00  lea     rax, [rsp+6A8h+var_608]
0x180112a08  cmp     qword ptr [rsp+6A8h+var_5F8+8], 0Fh
0x180112a11  cmova   rax, qword ptr [rsp+6A8h+var_608]
0x180112a1a  mov     [rsp+6A8h+var_5E0], rax
0x180112a22  lea     r9, [rsp+6A8h+var_640]
0x180112a27  lea     r8, [rsp+6A8h+var_608]
0x180112a2f  lea     rdx, [rsp+6A8h+var_580]
0x180112a37  lea     rcx, [rsp+6A8h+var_318]
0x180112a3f  call    ??$get@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV345@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::chrono::duration<__int64,std::ratio<1,1000>>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180112a44  nop
0x180112a45  lea     rcx, [rsp+6A8h+var_608]
0x180112a4d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180112a52  lea     rsi, [rsp+6A8h+var_2F0]
0x180112a5a  cmp     [rsp+6A8h+var_2D8], 0Fh
0x180112a63  cmova   rsi, [rsp+6A8h+var_2F0]
0x180112a6c  mov     rcx, [rsp+6A8h+var_2E0]
0x180112a74  test    rcx, rcx
0x180112a77  jz      short loc_180112AAB
  ... truncated ...
```
